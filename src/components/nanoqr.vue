<script lang="ts">
import * as QRCode from 'qrcode';
import copy from 'copy-to-clipboard';
import { defineComponent } from "vue";

export default defineComponent({
    props: ['address','width','height','hideText'],
    methods: {
        generate() {
            this.$nextTick(() => {
                var canvas = this.$refs.canvas;
                let options = {errorCorrectionLevel:'H',width:this.$props.width,height:this.$props.height} // H=high quality;
                console.log('props.address',this.$props.address);
                QRCode.toCanvas(canvas, this.$props.address,options, function (error) {
                  if (error) console.error(error)
                  console.log('success!');
                })
            });

        },
        copy(txt) {
            copy(txt);
            const thiz = this;
            thiz.$data.justCopied = true;
            setTimeout(() => {
                thiz.$data.justCopied=false;
            },6000);
        }

    },
    data() {
        return { justCopied:false };
    },
    mounted() {
            this.generate();
    },
});
</script>

<template>
    <canvas :width=width :heigh=height ref="canvas" class="nanoqrcanvas"></canvas>
  <div v-if="!hideText">
<h3 style="color:#ddd">Scan or Click Below to Copy Our Public Nano Address</h3>
<b
@click="copy(address)" 

 style="cursor:pointer;background: rgb(32, 156, 233) none repeat scroll 0% 0%; margin: 16px 4px 4px; padding: 16px 24px; border-radius: 5px; color: white; display: block; word-break: break-all;">{{address}}</b>



      <div v-if="justCopied" class='simpleSuccessPopup'>Copied address</div>
  </div>

</template>


<style>
.simpleSuccessPopup {
    position:fixed;
    left:16px;
    top:16px;
    background:green;
    color:white;
    -webkit-border-radius:9px;
    -moz-border-radius:9px;
    border-radius:9px;
    padding:12px;
  animation: cssAnimation 0s 5s forwards;
  opacity: 1; 
}

@keyframes cssAnimation {
  to   { opacity: 0; }
}
</style>
