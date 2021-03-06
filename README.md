# node-vipps

Node Vipps SDK for easy Vipps integration in Node.JS. Generic Vipps Node integration with specific support for the [OSSPIM headless ecommerce service](https://ossgroup.com/).

OSSPIM enables you to build your next-gen e-commerce business by the help of [Fast GraphQL API Service](https://ossgroup.com/product/graphql-commerce-api) backed by super structured [Product Information Management (PIM)](https://ossgroup.com/product/product-information-management)

You can view the required body models documented in [Vipps swagger documentation](https://vippsas.github.io/vipps-ecom-api/)

## Install

```
yarn add @osspim/node-vipps
```

## Usage

### Initiate the client<br/>

```
const client = new VippsClient({
    id: "MY_VIPPS_CLIENT_ID",
    secret: "MY_VIPPS_CLIENT_SECRET",
    subscriptionId: "MY_VIPPS_SUB_KEY",
    testDrive: isProd ? false : true
});
```

### Initiate a payment<br/>

```
await client.initiatePayment({order:VippsCheckoutModel});
```

### Capture a payment<br/>

```
await client.capture({ orderId: VippsOrderId, body: VippsCaptureBodyModel });
```

### Refund a payment<br/>

```
await client.refund({ orderId: VippsOrderId, body: VippsRefundBodyModel });
```

### Get order payment details<br/>

```
await client.getOrderDetails({ orderId: VippsOrderId});
```

### Get an access token<br/>

```
await client.getAccessToken();
```
# node-vipps
