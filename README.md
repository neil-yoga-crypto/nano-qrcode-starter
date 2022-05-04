#### Nano QR Code Starter
![nano](nano.gif)

This template should help get you started developing your Nano checkout.


The template uses Vue 3 with Vite for optimal (development) speed.

## Install
Be sure to replace the wallet address in src/App.vue.
```
npm install
npm run dev
```

If you're already have an existing Vue 3 project you can copy the component:
``
cp /src/components/nanoqr.vue [your_project_component_dir]
```

And include the Nano QRCode component via:
```
<nanoqr :address=address :width="360" :height="360" :hideText=false />
```
