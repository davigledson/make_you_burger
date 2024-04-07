<template>
    <div>
        
        <div>
            <mensagem :msg="msg" v-show="msg"/>
            <form action="" id="burger-form" @submit="createBurguer">
                <div class="input-container">
                    <label for="nome">
                        nome do cliente
                    </label>
                    <input type="text" id="nome" v-model="nome" placeholder="digite o seu nome">
                </div>

                <div class="input-container">
                    <label for="pao">Escolha o pão</label>
                    <select name="pao" id="pao" v-model="pao">
                        <option value="">Selecione o pão</option>
                        <option v-for="pao in paes" :key="pao.id" :value="pao.tipo">{{ pao.tipo }}</option>
                    </select>

                </div>

                <div class="input-container">
                    <label for="carne">Escolha a carne do seu Burguer</label>
                    <select name="carne" id="carne" v-model="carne">
                        <option value="">Selecione o tipo de carne</option>

                        <option v-for="carne in carnes" :key="carne.id" :value="carne.tipo">{{ carne.tipo }}</option>
                    </select>

                </div>

                <div id="opcionais-container" class="input-container">
                    <label id="opcionais-title" for="opcionais">selecione os opcionais</label>

                    <div class="checkbox-container" v-for="opcional in opcionaisdata" :key="opcional.id">

                        <input type="checkbox" name="opcionais" v-model="opcionais" :value="opcional.tipo">
                        <span>{{ opcional.tipo }}</span>

                    </div>



                </div>


                <div class="input-container">
                    <input type="submit" class="submit-btn" value="Criar meu Burger">

                </div>
            </form>
        </div>
    </div>

</template>

<script>
import Mensagem from './Mensagem.vue'

export default {
    name: "BurgerForm",
    data() {
        return {
            paes: null,
            carnes: null,
            opcionaisdata: null,
            nome: null,
            pao: null,
            carne: null,
            opcionais: [],
            status: "solicitado",
            msg: null
        }
    },
    methods: {
        async getIngredientes() {
            const req = await fetch("http://localhost:3000/ingredientes")
            const data = await req.json();


            this.paes = data.paes
            this.carnes = data.carnes
            this.opcionaisdata = data.opcionais

            // this.msg = null

        },
        async createBurguer(e) {
            e.preventDefault();
            const data = {
                nome: this.nome,
                carne: this.carne,
                pao: this.pao,
                opcionais: Array.from(this.opcionais),
                status: "solicitado"
            }

            const dataJson = JSON.stringify(data);
            const req = await fetch("http://localhost:3000/burgers", {
                method: "POST",
                headers: { "Content-Type": "application/json" },
                body: dataJson
            });

            const res = await req.json();

            //colocar uma msg de sistema
            this.msg = `Pedido N° ${res.id} realizado com sucesso`
            //limpar msg
            setTimeout(() => this.msg="", 3000);

            //limpar os campos
            this.nome = ""
            this.carne = ""
            this.pao = ""
            this.opcionais = ""
        },

    },
    mounted() {
        this.getIngredientes()
    },
    components: {
        Mensagem
    }
}
</script>

<style>
#burger-form {
    max-width: 400px;
    margin: 0 auto;

}

.input-container {
    display: flex;
    flex-direction: column;
    margin-bottom: 20px;

}

label {
    font-weight: bold;
    margin-bottom: 15px;
    color: #222;
    padding: 5px 10px;
    border-left: 4px solid gold;
}

input,
select {
    padding: 5px 15px;
    width: 300px;

}

#opcionais-container {
    flex-direction: row;
    flex-wrap: wrap;
}

#opcionais-title {
    width: 100%;

}

.checkbox-container {
    display: flex;
    align-items: flex-start;
    width: 50%;
    margin-bottom: 20px;
}

.checkbox-container input,
.checkbox-container span {
    margin-left: 6px;
    font-weight: bold;
}

.submit-btn {
    background-color: #222;
    color: gold;
    font-weight: bold;
    padding: 10px;
    margin: 0 auto;
    cursor: pointer;
    transition: .5s;

}

.submit-btn:hover {
    background-color: transparent;
    color: #222;
}
</style>