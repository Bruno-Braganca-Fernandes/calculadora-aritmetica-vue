<template>
    <div class="calculadora">
        <input type="number" v-model="num1" @input="calcular" placeholder="Digite o 1º número" />

        <input type="number" v-model="num2" @input="calcular" placeholder="Digite o 2º número" />

        <select v-model="operacao" @change="calcular">
            <option value="+">Soma</option>
            <option value="-">Subtração</option>
            <option value="*">Multiplicação</option>
            <option value="/">Divisão</option>
        </select>

        <p>Resultado: {{ resultado }}</p>
    </div>
</template>

<script>
export default {
    name: 'Calculadora',
    data() {
        return {
            num1: 0,
            num2: 0,
            operacao: '+',
            resultado: 0
        }
    },
    methods: {
        calcular() {
            const n1 = parseFloat(this.num1)
            const n2 = parseFloat(this.num2)

            switch (this.operacao) {
                case '+':
                    this.resultado = n1 + n2
                    break
                case '-':
                    this.resultado = n1 - n2
                    break
                case '*':
                    this.resultado = n1 * n2
                    break
                case '/':
                    this.resultado = n2 !== 0 ? (n1 / n2).toFixed(2) : 'Erro: divisão por zero'
                    break
            }
        }
    },
    mounted() {
        this.calcular()
    }
}
</script>

<style scoped>
.calculadora {
    max-width: 400px;
    margin: auto;
    padding: 30px;
    border: 2px solid #ccc;
    border-radius: 10px;
    text-align: center;
}

input,
select {
    margin: 10px -10px;
    padding: 8px;
    width: 100%;
}
</style>
