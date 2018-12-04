
<template>
    <div>
        <div v-html="style"></div>
            <pre v-highlight>
                <code>
                    {{march}}
                </code>
            </pre>
    </div>
</template>

<script>
    export default{
        components:{

        },
        data(){
            return{
                march:'',
                final:
`
/*  HR您好！      我叫王俊坤
    马上过年啦！
    希望自己能在年前找到一份合适的工作，所以有了这份简历咯!
    说干就干，我这就开始！ 
    先给元素加上过渡吧！*/  
*{
    transition:.3s;
}
    /* 字体调大一点 */                                            
body{
    font-size:17px;
    /* 加个粗 加个背景 加个字体颜色*/
    
    background:#002738;
    color:#eee;
} 
`
            }
        },
        methods:{
            load(){
                var i=0
                setInterval(()=>{
                    this.march=this.final.substring(0,i)
                    i++
                },20)
            }
        },
        created(){
            this.load()
        },
        computed:{
            style(){
                return '<style>' + this.march + '</style>'
            }
        },
    }
</script>
<style>
.code{
    background:#002738;
}
</style>