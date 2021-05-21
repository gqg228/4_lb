<template>
    <FlexboxLayout flexWrap = "wrap" class="v" backgroundColor ="#f2dac3" >
    <TextField v-model="res" editable="false" width =100%  class="inp" />
    <Button v-for="(number,k)  in numb" @tap="input(number)" :text="number" v-bind:key = "k" backgroundColor ="#cc9b6d" class="btns" fontSiz = "52" />
    <Button v-for="(operation, k) in oprt" @tap="input(operation)" :text="operation" v-bind:key="k"  backgroundColor ="#a0937d"/> 
    <Button width =100% @tap="ress()" text="=" backgroundColor ="#cc9b6d"/>
    </FlexboxLayout>
</template>

<script>
    export default{
        data: function(){
            return{
                
                numb :['1','2','3','4','5','6'],
                oprt :['-','+','.','+','*','C',],
                res: ' '
                
            }
        },
        methods:{
            input(up){
                if(up==='C')
                    this.res = ''

                if(this.res == ' '&& this.oprt.includes(up,1)==true)
                    this.res = this.res
                else if(this.oprt.includes(up,0) == true && this.oprt.includes(this.res.slice(-1),0)==true)
                    this.res = this.res
                else if(up !='C')
                    this.res = this.res + up    
                
            },
            ress(){
                if(this.res != '')
                    this.res = eval(this.res).toString()
            }
        }

    }




</script>

<style>
    .inp{
        text-align: right;
    }
    .btns{
        font: 900;
        
    }

</style>