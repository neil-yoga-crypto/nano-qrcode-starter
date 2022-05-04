#### Nano QR Code Starter
![nano](nano.gif)

The template uses Vue 3 with Vite for optimal (development) speed.

Live example: https://every.yoga/nano/

Happy coding, and namaste 🙏! 

## Install
Be sure to replace the wallet address in src/App.vue.
```
git clone https://github.com/neil-yoga/nano-qrcode-starter
npm install
npm run dev
```

## Install in existing Vue 3 project
In case you already have an existing Vue 3 project, and you just want to use the QR code component, you can easily install the dependencies and copy the component like this:
```
npm install copy-to-clipboard --save
npm install qrcode --save
git clone https://github.com/neil-yoga/nano-qrcode-starter
cp nano-qrcode-starter/src/components/nanoqr.vue [your_project_component_dir]
```

And include the component in your template via:
```
<nanoqr :address=address :width="360" :height="360" :hideText=false />
```

## Build & Deploy
When using a subdirectory be sure to replace the base variable in ./vite.config.js.
```
npm run-script build
zip -r dist.zip dist
# upload/unarchive on webserver
```

### Bonus: Keep things alive
```
// Enjoy the free code sharing. 
//
// ☯️ If you used my code to save time,
//  consider donating eco-friendly crypto:
```

```
nano_3boxqk5q56xsz8ufrw9srrz4pta6ffbkrg9j31aqziz8wtnr6j68ci7s4cnc
```

```
// It matters: Everything is an energy exchange ⚡.
//
//
// ^ Also feel free to copy this template for your own projects and replace the wallets.
// 🙏 You deserve to be happy and free.
```

### Nano?
<a style="color:black;font-size:15px;" href="https://nano.org">Zero Fees, Eco-Friendly, Instant Payments</a>
