# BulkSMSNigeria API Wrapper Documentation

The BulkSMSNigeria API Wrapper is a Python library that provides a convenient interface for sending SMS messages using the BulkSMSNigeria SMS gateway. This library simplifies the process of sending messages to single or multiple recipients, retrieving account balance, and obtaining delivery reports.

Installation
To use the BulkSMSNigeria API Wrapper, you need to 

1. Create an account on BulkSMSNigeria.com (www.bulksmsnigeria.com/register)
2. Verify at least one of your contacts (i.e., email or phone number).
3. Fund your account with at least 500NGN.
4. Generate an API Token on the API Settings Page (www.bulksmsnigeria.com/app/api-settings)
5. Maintain a minimum balance of 100NGN in the account.

6.  Have Python installed. You can install the library using pip:
```
pip install bulksmsnigeria
```

## Getting Started

To begin using the BulkSMSNigeria API Wrapper, you need to import the necessary module and initialize an instance of the BulkSMSNigeria class:

```
from bulksmsnigeria import BulkSMSNigeria

# Initialize the BulkSMSNigeria object with your API token
api_token = 'YOUR_API_TOKEN'
bulksms = BulkSMSNigeria(api_token)

```
Replace YOUR_API_TOKEN with your actual API token obtained from BulkSMSNigeria

## Sending SMS
### Sending SMS to a Single Recipient
You can use the sendToOne method to send an SMS to a single recipient:
```
sender = 'SENDER_NAME'
recipient = 'RECIPIENT_PHONE_NUMBER'
body = 'MESSAGE_CONTENT'

response = bulksms.sendToOne(sender, recipient, body)

```

`sender` (str): The name that will be displayed as the sender of the message.
`recipient` (str): The phone number of the recipient.
`body` (str): The content of the message.

The method returns a dictionary with the following keys:
`status` (int): The HTTP status code of the request.
`response` (dict): The JSON response received from the BulkSMSNigeria API.

### Sending SMS to Multiple Recipients
You can use the sendToMany method to send an SMS to multiple recipients:
```
sender = 'SENDER_NAME'
recipients = ['RECIPIENT_PHONE_NUMBER_1', 'RECIPIENT_PHONE_NUMBER_2', ...]
body = 'MESSAGE_CONTENT'

response = bulksms.sendToMany(sender, recipients, body)
```

`sender` (str): The name or phone number that will be displayed as the sender of the message.
`recipients` (list): A list of phone numbers of the recipients.
`body` (str): The content of the message.

The method returns a dictionary with the following keys:
`status` (int): The HTTP status code of the request.
`response` (dict): The JSON response received from the BulkSMSNigeria API.

## Retrieving Account Balance
To retrieve your account balance, you can use the getWalletBalance method:
```
response = bulksms.getWalletBalance()
```

The method returns a dictionary with the following keys:
`status` (int): The HTTP status code of the request.
`response` (dict): The JSON response received from the BulkSMSNigeria API.

## Retrieving Delivery Report
You can retrieve the delivery report of a sent message using the getDeliveryReport method:
```
message_id = 'MESSAGE_ID'
response = bulksms.getDeliveryReport(message_id)
```

`message_id` (str): The unique ID of the message for which you want to obtain the delivery report.

The method returns a dictionary with the following keys:
`status` (int): The HTTP status code of the request.
`response` (dict): The JSON response received from the BulkSMSNigeria API.

## Contributing
We welcome contributions from the community! If you would like to contribute to the BulkSMSNigeria Python library, please follow these guidelines:

1. Fork the repository and create your branch from the `main` branch.
2. Make your changes and ensure that the code passes all tests.
3. Write clear and concise commit messages.
4. Submit a pull request to the `main` branch.

### Code Style
Please adhere to the following code style guidelines:
- Use PEP 8 style guide for Python code.
- Write clear and meaningful variable and function names.
- Include comments to explain complex logic or important details.
- Follow the existing code formatting and structure.

### Bug Reports and Feature Requests
If you encounter any bugs or have suggestions for new features, please open an issue on the GitHub repository. Provide a clear description of the problem or feature request and any relevant details.

### Contact
If you have any questions or need assistance, you can reach out to us.

We appreciate your contributions and thank you for helping improve the BulkSMSNigeria Python library!