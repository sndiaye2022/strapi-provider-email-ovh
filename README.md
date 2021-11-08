# strapi-provider-email-ovh
This package is an email provider for the headless CMS [Strapi](https://github.com/strapi/strapi).
You can use this provider to send mail programmatically with `strapi-plugin-email`.

This provider enables you to send email with OVH.

## Installation

```bash
# using yarn
yarn add strapi-provider-email-ovh

# using npm
npm install strapi-provider-email-ovh --save
```

## Setup

1) Use same cridentials when you connect https://www.ovh.com/fr/mail/
2) Configure the provider in `config/plugins` with cridentials in 1)

| Variable                  | Type                    | Description                                                                                                                         | Required | Default   |
| ------------------------- | ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | -------- | --------- |
| provider                  | string                  | The name of the provider you use                                                                                                    | yes      |           |
| providerOptions           | object                  | Provider options                                                                                                                    | yes      |           |
| providerOptions.user  | string                  | An existing email address within your account https://www.ovh.com/fr/mail/                                                                                        | yes      |           |
| providerOptions.pass  | string                  | The password of the account                                                                                                   | yes      |           |
settings	| object |	Settings |	no	| {}
settings.defaultFrom |	string	| Default sender mail address, exist in domain	| no	| undefined
settings.defaultReplyTo |	string | array	Default address or addresses the receiver is asked to reply to	| no	| undefined


### Example

**Path -** `config/plugins.js`

```js
module.exports = ({ env }) => ({
  // ...
  email: {
    provider: 'ovh',
    providerOptions: {
      user: "myemail@example.com",
      pass: "password",
    },
    settings: {
      defaultFrom: 'myemail@example.com',
      defaultReplyTo: 'myemail@example.com',
    },
  },
  // ...
});
```

## Resources

- [MIT License](LICENSE.md)

## Links

- [Strapi website](http://strapi.io/)
- [Strapi community on Slack](http://slack.strapi.io)
- [Strapi news on Twitter](https://twitter.com/strapijs)
