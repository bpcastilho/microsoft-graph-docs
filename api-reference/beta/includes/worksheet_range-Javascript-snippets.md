
```Javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const workbookRange = {
  address: "address-value"
};

let res = await client.api('/me/drive/items/{id}/workbook/worksheets/{id|name}/Range')
	.version('beta')
	.post(workbookRange);

```