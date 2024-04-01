<template>

    <div id="burger-table">
        <div>
            <div id="burger-table-heading">
                <div class="order-id">#:</div>
                <div>Cliente:</div>
                <div>Pão:</div>
                <div>Carne:</div>
                <div>Opcionais:</div>
                <div>Ações:</div>
            </div>
            <div id="burger-table-rows">
                <div class="order-id">#:</div>
                <div class="burger-table-row">1
                    <div>João</div>
                    <div>Pão de Trigo</div>
                    <div>Maminha</div>

                    <ul>
                        <li>Salame</li>
                        <li>Tomate</li>
                    </ul>

                    <select name="status" class="status">
                        <option value="">Selecione o status do Hamburger</option>
                    </select>
                    <button class="delete-btn">Deletar</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Dashboard"
}
</script>

<style scoped>
#burger-table {
    max-width: 1200px;
    margin: 0 auto;
}

#burger-table-heading,
#burger-table-rows,
.burger-table-row {
    display: flex;
    flex-wrap: wrap;
}

#burger-table-heading {
    font-weight: bold;
    padding: 12px;
    border-bottom: 3px solid #333;
}

.burger-table-row {
    width: 100%;
    padding: 12px;
    border-bottom: 1px solid #CCC;
}

#burger-table-heading div,
.burger-table-row div {
    width: 19%;
}

#burger-table-heading .order-id,
.burger-table-row .order-number {
    width: 5%;
}

select {
    padding: 12px 6px;
    margin-right: 12px;
}

.delete-btn {
    background-color: #222;
    color: #fcba03;
    font-weight: bold;
    border: 2px solid #222;
    padding: 10px;
    font-size: 16px;
    margin: 0 auto;
    cursor: pointer;
    transition: .5s;
}

.delete-btn:hover {
    background-color: transparent;
    color: #222;
}
</style>