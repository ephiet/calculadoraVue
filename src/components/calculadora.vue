<template>
    <div class="calcul">
        <h4>Ingrese dos números y seleccione una operación</h4>

        <form class="form">
            <div>
                <input v-model="opA" type="number" class="input-a">
            </div>

            <select v-model="operacion" class="select-operacion">
                <option value="+">+</option>
                <option value="-">-</option>
                <option value="*">*</option>
                <option value="/">/</option>
            </select>

            <div>
                <input v-model="opB" type="number" class="input-b">
            </div>
            
            <div>
              <button @click.prevent="resultadoFinal()" type="submit" class="btn">Calcular</button>
          </div>
        </form>
        <hr>
        <div class="display-resultado">
            <h4>Resultado:</h4>
            <p class="display-operandoa">{{opA}}</p>
            <p class="display-operacion">{{operacion}}</p>
            <p class="display-operandob">{{opB}}</p>
            <p class="display-igual">{{igual}}</p>
            <p class="display-total">{{resultado}}</p>
        </div>
    </div>
</template>

<script>
export default {
  name: 'calculadora',
  props: {
    msg: String
  },
  data: function() {
    return {
        opA: "",
        opB: "",
        operacion: "",
        resultado: "",
        igual: "",
        
    }},
    methods: {
        resultadoFinal() {
          
            if (this.resultado == 0){
            switch (this.operacion) {
              case "+":
                this.resultado = parseInt(this.opA) + parseInt(this.opB);
                break;
              case "-":
                this.resultado = parseInt(this.opA) - parseInt(this.opB);
                break;
              case "*":
                this.resultado = parseInt(this.opA) * parseInt(this.opB);
                break;
              case "/":
                this.resultado = parseInt(this.opA) / parseInt(this.opB);
                break;
            }
            }
            else {
              this.resultado = 0;
              switch (this.operacion) {
              case "+":
                this.resultado = parseInt(this.opA) + parseInt(this.opB);
                break;
              case "-":
                this.resultado = parseInt(this.opA) - parseInt(this.opB);
                break;
              case "*":
                this.resultado = parseInt(this.opA) * parseInt(this.opB);
                break;
              case "/":
                this.resultado = parseInt(this.opA) / parseInt(this.opB);
                break;
            }
            }
            this.igual = "="
        },
        limpiar() {
        this.opA= "";
        this.opB= "";
        this.operacion= "";
        this.resultado= "";
        this.igual= "";
        },
    }
}
</script>

<style scoped>
.calcul {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background-color:white;
  padding: 4em;
  margin-top: 4em;
}
.form {
  display: flex;
  flex-wrap: wrap;
  margin-top: 2em;
}
.btn{
  background-color: rgb(250, 101, 163);
  color: white;
  font-weight: bold;
  margin: 0 10px 0 10px;
  height: 60%;
}
.input-a, .input-b {
  margin: 0 1em 2em 1em;
  padding: 1em;
}
.select-operacion {
  padding:0.5em;
  margin: 0 1em 2em 1em;
}
.display-resultado{
  display: flex;
  flex-wrap: wrap;
  width:100%;
}
.display-operandoa, .display-operandob, .display-total{
  text-align: center;
  margin: 1em 0.5em 1em 0.5em;
  font-size: 2em;
  font-family: monospace;
 }
.display-operacion, .display-igual{
  text-align: center;
  margin: 1em 0.5em 1em 0.5em;
  font-family: monospace;
  font-size: 2em;
}

</style>
