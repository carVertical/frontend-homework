# Frontend Homework Assignment

Build a simplified purchase funnel that collects order details and completes the purchase.

## Design

[View in Figma](https://www.figma.com/file/5X88xmrbshv98i9w1ywut4/Frontend-Homework-Assignment?node-id=0%3A1)

Click the <kbd>▶</kbd> button in the toolbar to view an interactive prototype:

<img src="https://d33v4339jhl8k0.cloudfront.net/docs/assets/5aa962fe2c7d3a2c4983093d/images/5d9420f12c7d3a7e9ae1e571/file-SiluksfJfC.png" alt="Figma Presentation View" />

## Endpoints

### Mock API

This mock API is also bundled in the repo and runs with `yarn dev`, so you can use it locally instead of the hosted version below.

[cv-mock-api.vercel.app](https://cv-mock-api.vercel.app)

- Get packages: [`GET /api/packages`](https://cv-mock-api.vercel.app/api/packages)
- Get VAT rates: [`GET /api/vat-rates`](https://cv-mock-api.vercel.app/api/vat-rates)
- Create order: `POST /api/orders`

### IP API

[ipapi.co](https://ipapi.co)

- Get user’s country: [`GET ipapi.co/json`](https://ipapi.co/json)

## Requirements

- [ ] Build the purchase funnel UI to match the Figma design
- [ ] Fetch packages from `GET /api/packages`
- [ ] Apply the correct VAT to the price: fetch VAT rates from `GET /api/vat-rates` and match one to the user’s country (from `GET ipapi.co/json`). If the user’s country isn’t in the VAT rates, apply 0% VAT
- [ ] Execute purchase by sending order details to `POST /api/orders` with the following payload (replace with actual values):
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
- [ ] Validate buyer inputs with sensible constraints and clear error messaging
- [ ] Write meaningful tests
- [ ] Share code as a private repo on GitHub (**suggested repo name format**: `name-s-cv-homework`). Add [@and1-lt](https://github.com/and1-lt/) as a collaborator for review
- [ ] `README` should include instructions on how to run the app
- [ ] Deploy the app somewhere (deployed preview link must follow pattern `name-s.domain`, for example `john-d.vercel.app`)

## Extra points (optional)

Feel free to go further – but it’s _completely optional_ and extends the scope. We’d rather see the core done well. A few ideas:

- Session persistence – refreshing the page keeps the user’s progress
- Microanimations – transitions and small touches that make the funnel feel alive
- Loading states – skeletons and the like
- Accessibility – keyboard navigation, focus management, ARIA where it counts
- Your own ideas – surprise us

## Notes

- You can bootstrap and structure the app however you want, using any modern stack – this repo is just a starting point
- If you’re unsure on how some interaction should work, just use your best judgement ✌️
