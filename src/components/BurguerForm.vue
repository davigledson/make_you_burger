<template>
    <div>
        <p> Componente de mensagem</p>
        <div>
            <form action="" id="burger-form">
                <div class="input-container">
                    <label for="nome">
                        nome do cliente
                    </label>
                    <input type="text" id="nome" v-model="nome" placeholder="digite o seu nome">
                </div>

                <div class="input-container">
                    <label for="pao">Escolha o pão</label>
                    <select name="pao" id="pao">
                        <option value="">Selecione o pão</option>
                        <option value="integral">Integral</option>
                    </select>

                </div>

                <div class="input-container">
                    <label for="carne">Escolha a carne do seu Burguer</label>
                    <select name="carne" id="carne" v-model="carne">
                        <option value="">Selecione o tipo de carne</option>
                        <option value="integral">Maminha</option>
                    </select>

                </div>

                <div id="opcionais-container" class="input-container">
                    <label id="opcionais-title" for="opcionais">selecione os opcionais</label>

                    <div class="checkbox-container">
                        <input type="checkbox" name="opcionais" v-model="opcionais" value="salame">
                        <span>salame</span>
                    </div>
                    <div class="checkbox-container">
                        <input type="checkbox" name="opcionais" v-model="opcionais" value="salame">
                        <span>salame</span>
                    </div>
                    <div class="checkbox-container">
                        <input type="checkbox" name="opcionais" v-model="opcionais" value="salame">
                        <span>salame</span>
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
export default {
    name: "BurgerForm",
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