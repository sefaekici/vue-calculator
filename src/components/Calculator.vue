<template>
    <div class="calculator">
        <div class="calculator-panel">399,981</div>
        <div class="calculator-keys">
            <div class="row">
                <button>7</button>
                <button>8</button>
                <button>9</button>
                <button class="special-key">DEL</button>
            </div>
            <div class="row">
                <button>4</button>
                <button>5</button>
                <button>6</button>
                <button>+</button>
            </div>
            <div class="row">
                <button>1</button>
                <button>2</button>
                <button>3</button>
                <button>-</button>
            </div>
            <div class="row">
                <button>.</button>
                <button>0</button>
                <button>/</button>
                <button>x</button>
            </div>
            <div class="row">
                <button class="special-key large-button" >RESET</button>
                <button class="large-button eq-key">=</button>
            </div>
        </div>
    </div>
</template>


<script>
export default {
    
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
            width: 400px;
            height: 90px;
            font-size: 24px;
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
                    transition: opacity .6s;
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