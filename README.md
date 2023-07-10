<!-- @format -->

# react-klasha

This is a react library for implementing klasha payment gateway

## Demo

![Demo](App.png?raw=true 'Demo Image')

## Get Started

This React library provides a wrapper to add Klasha Payments to your React application

### Install

```sh
npm install klash-pay --save
```

or with `yarn`

```sh
yarn add klasha-pay
```

### Usage

```javascript
    import React from 'react';
// import the library
import { useKlashaPayment, KlashaButton, KlashaConsumer, KlashaHookExample } from 'react-klasha';

const App = () => {
  const [email, setEmail] = React.useState('klashapps@klasha.com');
  const [phoneNumber, setPhoneNumber] = React.useState('+2347038521460');
  const [merchantKey, setMerchantKey] = React.useState('GByi/gkhn5+BX4j6uI0lR7HCVo2NvTsVAQhyPko/uK4=');
  const [amount, setAmount] = React.useState(1000);
  const [txRef, setTxRef] = React.useState(String(Math.floor(Math.random() * 1000000000) + 1));
  const [businessId] = React.useState('1');
  const [fullname] = React.useState('Gabriel Godwin');

  const callBack = (response) => {
    console.log(response);
  };

  const kit = {
    currency: 'NG',
    phone_number: '+2347038521460',
    email: 'klashapps@klasha.com',
    fullname: 'Gabriel Godwin',
    tx_ref: '',
    paymentType: '',
  };

  const componentProps = {
    className: 'btn',
  };

  const initializePayment = () => {
    // implementation for Klasha Consumer Initialization
  };

  return (
    <div>
      <KlashaHookExample className="btn" />
    </div>
    <div>
      <p>
        <KlashaButton
          text="Make Payment"
          className="payButton"
          callBack={callBack}
          disabled={true} // disable payment button
          embed={true} // payment embed in your app instead of a pop up
          fullname={fullname}
          email={email}
          phone_number={phoneNumber}
          amount={amount}
          merchantKey={merchantKey}
          businessId={businessId}
          tx_ref={txRef}
          kit={kit}
          tag="button" // it can be button or a or input tag
        />
      </p>
    </div>
    <div>
      <KlashaConsumer {...componentProps} className="btn">
        {({ initializePayment }) => (
          <button onClick={() => initializePayment()}>Klasha Consumer Implementation</button>
        )}
      </KlashaConsumer>
    </div>
  );
};

export default App;
;
```

For more information checkout [klasha's documentation](https://documenter.getpostman.com/view/8963555/TzJoFgHh)

## Deployment

REMEMBER TO CHANGE THE MID WHEN DEPLOYING ON A LIVE/PRODUCTION SYSTEM

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b feature-name`
3. Commit your changes: `git commit -am 'Some commit message'`
4. Push to the branch: `git push origin feature-name`
5. Submit a pull request

Thanks!
Klasha.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
