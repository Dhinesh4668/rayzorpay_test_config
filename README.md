### razorpay test

# steps 
1. create the rayzor pay acc 

2. geerate the test payment key 
   `ex: rzp_kjhskjfhsjkfh998yu8` 

3. creat the one reactnative app 
   ```bash
   npx reactnative init <appname>
   ```
   * next 

4. install the razorpay package 

   ```bash 
   # using npm
   npm install react-native-razorpay --save

   # yarn 
   yarn add react-native-razorpay --save
   
   ```

5. config the button 

   ```JSX

   //import button components

   <Button titel="paymet:"  onPress={()=>{
      var options = {
         description: 'Credits towards consultation',
         image: 'https://i.imgur.com/3g7nmJC.jpg',
         currency: 'INR',
         key: '<YOUR_KEY_ID>',
         amount: '5000',
         name: 'Acme Corp',
         order_id: 'order_DslnoIgkIDL8Zt',//Replace this with an order_id created using Orders API.
         prefill: {
            email: 'gaurav.kumar@example.com',
            contact: '9191919191',
            name: 'Gaurav Kumar'
         },
         theme: {color: '#53a20e'}
      }
      RazorpayCheckout.open(options).then((data) => {
         // handle success
         alert(`Success: ${data.razorpay_payment_id}`);
      }).catch((error) => {
         // handle failure
         alert(`Error: ${error.code} | ${error.description}`);
      });
   }} />

   ```

6. make the test payment

   testpayment credential , refer razorpay doc [ref](https://razorpay.com/docs/payments/payment-gateway/react-native-integration/standard/test-integration/)

7. run the application 
   ```bash 
   # android
   npm run android 

   # ios
   npm pod-install

   npm run ios
   ```

