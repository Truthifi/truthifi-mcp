# Security and privacy

- **Sign-in:** OAuth with Dynamic Client Registration. You sign in to Truthifi in your browser; your assistant receives a token for Truthifi, never your password.
- **No bank credentials in chat:** accounts are linked on Truthifi's own secure page (`connect_account` only returns a link).
- **No changes at your bank or brokerage:** nothing your assistant does through Truthifi can move money, place trades or change settings at your bank or brokerage.
- **Changes inside Truthifi:** three tools change data inside Truthifi only (see [tools.md](tools.md)).
- **What the server receives:** the requests your assistant makes for your own data, plus an optional one-line note on what you're trying to do (no names, amounts or account details), saved with a record of each call for safety monitoring and to improve the product. Data the tools return goes to the AI assistant you chose and is handled under that provider's terms. See the [privacy policy](https://truthifi.com/privacy).
- **Stopping access:** remove the Truthifi connector in your assistant. To revoke access on Truthifi's side, or to ask for access to or deletion of your data, see the [privacy policy](https://truthifi.com/privacy) or email support@truthifi.com.
- Privacy policy: <https://truthifi.com/privacy> · Terms: <https://truthifi.com/terms> · Security: <https://truthifi.com/security>
- Report a vulnerability: see [SECURITY.md](../SECURITY.md).
