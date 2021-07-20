<template>
    <div class="conversor">
        <h2>{{moedaA}} Para {{moedaB}}</h2>
        <input type="text" v-model="moedaA_value" v-bind:placeholder="moedaA">
        <input type="button" value="Converter" v-on:click="converter">
        <h2>{{moedaB_value}}</h2>
    </div>
</template>

<script>
    // Exportando componente
    export default{
        // Definindo nome a passando propriedades
        name: "Conversor",
        props: ["moedaA", "moedaB"],
        // Função data, dados do componente
        data(){
            return{
                moedaA_value: "",
                moedaB_value: 0
            }
        },
        methods: {
            converter(){
                let de_para = this.moedaA + "_" + this.moedaB;
                let url = "https://free.currconv.com/api/v7/convert?q=" + de_para + "&compact=ultra&apiKey=d7a73235028e57f6ef85";

                fetch(url).then(res => {
                    return res.json();
                })
                .then(json => {
                    let cotacao = json[de_para];
                    this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2);
                    console.log(this.moedaB_value);
                });
            }
        }
    }
</script>

<style scoped>

.conversor {
    padding: 20px;
    background-color: #eee;
    border-radius: 5px;
    width: 300px;
    margin: 0 auto;
    
    margin-bottom: 15px;
}

</style>
