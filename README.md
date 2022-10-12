# Frontend Homework Assignment

Build a simplified purchase funnel that collects order details and executes the purchase.

## Design

[View in Figma](https://www.figma.com/file/5X88xmrbshv98i9w1ywut4/Frontend-Homework-Assignment?node-id=0%3A1)

Click <kbd>▶</kbd> button in the toolbar to view an interactive prototype:

<img src="https://d33v4339jhl8k0.cloudfront.net/docs/assets/5aa962fe2c7d3a2c4983093d/images/5d9420f12c7d3a7e9ae1e571/file-SiluksfJfC.png" alt="Figma Presentation View" />

## Endpoints

- Get packages: [`GET /packages`](https://run.mocky.io/v3/d6338d9d-a4ce-4054-9781-c0f0cfe2392d)
- Get VAT rates: [`GET /vatRates`](https://run.mocky.io/v3/208cbd1e-0d11-4b3e-b54e-5f17a2b46012)
- Get user’s country (IP geolocation): [`GET /ip`](https://ipapi.co/json/)
- Create order: [`POST /orders`](https://run.mocky.io/v3/7b3ca122-9107-42f6-ba84-1a3056849410)

## Requirements

- [ ] Fetch packages from `GET /packages`
- [ ] Apply a correct VAT to the price by fetching VAT rates from `GET /vatRates` and matching one of them with user’s country through `GET /ip`. If VAT rates’ endpoint does not contain user’s country, apply 0% VAT
- [ ] Execute purchase by sending order details to `POST /orders` with the following payload (replace with actual values):
  ```json
  {
    "packageId": "single",
    "buyer": {
      "firstName": "John",
      "lastName": "Doe",
      "email": "john.doe@example.com"
    },
    "vat": {
      "countryCode": "lt",
      "rate": 21
    },
    "price": {
      "currency": "EUR",
      "amount": 14.99,
      "grossAmount": 18.14,
      "vatAmount": 3.15
    }
  }
  ```
- [ ] Use [React Hooks](https://reactjs.org/docs/hooks-reference.html)
- [ ] Write at least one test
- [ ] Share code as a private repo on GitHub. Add [@and1-lt](https://github.com/and1-lt/) as a collaborator for review
- [ ] `README` should include instructions on how to run the app
- [ ] Deploy the app somewhere

## Notes

- You can bootstrap and structure the app however you want
- If you’re unsure on how some interaction should work, just use your best judgement
