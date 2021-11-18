<template>
    <div class="conversor">
        <h2>{{moedaA}} Para {{moedaB}}</h2>
        <input type="text" class="campo" v-model="moedaA_value" v-bind:placeholder="moedaA">
        <input type="button" class="button zoom" value="Converter" v-on:click="converter">
        <h2>{{moedaB_value}}</h2>
    </div>
</template>

<script>
export default {
    name: "Conversor",
    props: ["moedaA", "moedaB"],
    data(){
        return{
            moedaA_value: "",
            moedaB_value: ""
        }
    },
    methods: {
        converter(){
            let de_para = this.moedaA + "_" + this.moedaB;

            let url="https://free.currconv.com/api/v7/convert?q="+de_para+"&compact=ultra&apiKey=5173f2048710a40794b7";

            fetch(url)
            .then(response => {
                return response.json();
            })
            .then(json=>{
                let cotacao = json[de_para];
                this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2);
            })
        }
    }
}
</script>

<style scoped>

.conversor{
    padding: 20px;
    max-width: 300px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    border-radius: 30px;
}

.campo{
      background: transparent;
      color: white;
      border: 2px solid #51CC60;
      border-radius: 10px;
      outline: none;
}

.button{
      margin: 15px;
      font-family: "Verdana";
      font-size: 20px;
      background-color: #314559;
      color: #FFFFFF;
      cursor: pointer;
      border-color: #51CC60;
      border-radius: 100px;
      max-width: 120px;
}

.button:hover{
    background-color: #2b3d4e;
}

.zoom{
	transition: transform .2s; 
}

.zoom:hover {
	transform: scale(1.1);
}
</style>
