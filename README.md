# vue2.0----ref
vue.js 2.0 里面的ref 用法
 
 
 本文介绍了vue2里面  nextTick 与 ref  的具体使用方法，分享给大家，具体如下。
 
 
   
        
          例子：   点击按钮查看效果
            
               <div class="app">
                  <div ref="msgDiv">{{msg}}</div>
                  <div v-if="msg1">Message got outside $nextTick: {{msg1}}</div>
                  <div v-if="msg2">Message got inside $nextTick: {{msg2}}</div>
                  <div v-if="msg3">Message got outside $nextTick: {{msg3}}</div>
                  <button @click="changeMsg">
                      Change the Message
                  </button>
              </div>
              
            <script>
                new Vue({
                    el: '.app',
                    data: {
                        msg: 'Hello Vue.',
                        msg1: '',
                        msg2: '',
                        msg3: ''
                    },
                    methods: {
                  changeMsg:function() {
                     this.msg = "Hello world."
                     this.msg1 = this.$refs.msgDiv.innerHTML;
                    this.$nextTick(function(){
                        this.msg2 = this.$refs.msgDiv.innerHTML
                   })
                       this.msg3 = this.$refs.msgDiv.innerHTML
                    }
                  }
                })
            </script>

        
        
        
        
        
        
        
