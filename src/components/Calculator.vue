<template>
    <div class="calculator">
        <div class="calculator-panel">{{current==''? 0:current }}</div>
        <div class="calculator-keys">
            <div class="row">
                <button @click="append('7')">7</button>
                <button @click="append('8')">8</button>
                <button @click="append('9')">9</button>
                <button class="special-key" @click="removeFromEnd()">DEL</button>
            </div>
            <div class="row">
                <button @click="append('4')">4</button>
                <button @click="append('5')">5</button>
                <button @click="append('6')">6</button>
                <button @click="plus()">+</button>
            </div>
            <div class="row">
                <button @click="append('1')">1</button>
                <button @click="append('2')">2</button>
                <button @click="append('3')">3</button>
                <button @click="minus()">-</button>
            </div>
            <div class="row">
                <button @click="addDot()">.</button>
                <button @click="append('0')">0</button>
                <button @click="divide">/</button>
                <button @click="multiplication()">x</button>
            </div>
            <div class="row">
                <button class="special-key large-button" @click="clear()" >RESET</button>
                <button class="large-button eq-key" @click="equal()" >=</button>
            </div>
        </div>
    </div>
</template>


<script>
export default {
    data(){
        return{
            current:'',
            operator:null,
            previous:null,
            operatorClicked:false,
        }
    },
    methods:{
        clear(){
            this.current='';

        },
        append(num) {
            if (this.operatorClicked) {
                this.current = '';
                this.operatorClicked = false;
            }
            this.current = `${this.current}${num}`;
        },
        removeFromEnd(){
            if(this.operatorClicked){
                this.current='';
                this.operatorClicked=false;
            }
            let value='';
            for(var i=0;i<this.current.length-1;i++){
                value=value+this.current[i];
            }
            this.current=value;
        },
        addDot(){
            if (this.current.indexOf('.') === -1) {
                this.append('.');
            }
        },
        editPrevious() {
            this.previous = this.current;
            this.operatorClicked = true;
        },
        divide() {
            this.operator = (a, b) => b / a;
            this.editPrevious();
        },
        multiplication(){
            this.operator = (a, b) => a * b;
            this.editPrevious();
        },
        minus(){
            this.operator = (a, b) => b- a;
            this.editPrevious();
        },
        plus(){
            this.operator = (a, b) => a + b;
            this.editPrevious();
        },
        equal(){
            this.current = `${this.operator(
                parseFloat(this.current), 
                parseFloat(this.previous)
            )}`;
            this.previous = null;
        }
    }
}
</script>


<style lang="scss">
    @import "../assets/scss/_colors.scss";
    .calculator{
        margin-top: 2rem;
        width: 400px;
        height: 500px;
        display: flex;
        flex-direction: column;
        align-items: center;
        .calculator-panel{
            overflow: auto;
            width: 400px;
            height: 90px;
            font-size: 28px;
            background: $calculator-panel-background;
            display: flex;
            align-items: center;
            justify-content: flex-end;
            padding: 0 15px;
            border-radius: 5px;
            margin-bottom: 1.5rem;
            color: #fff;
        }

        .calculator-keys{
            border-radius: 5px;
            background: $calculator-background;
            width: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 1rem 1rem;
            .row{
                padding: 5px 5px;
                button{
                    border-radius: 5px;
                    border: none;
                    font-size: 24px;
                    width: 80px;
                    height: 50px;
                    transition: opacity .4s;
                    &:not(:last-child){
                        margin-right: 10px;
                    }
                    &:hover{
                        opacity: .5;
                    }
                }

                .special-key{
                    background: $button-background-colors;
                    color:#fff;
                }

                .large-button{
                    width: 170px;
                }

                .eq-key{
                    background:$equal-key-background;
                    color: #fff;
                }
            }
        }
    }


</style>