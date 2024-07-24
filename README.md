# Azure Storage Queue Reader

This Python script reads messages from an [Azure Storage Queue](https://docs.microsoft.com/en-us/azure/storage/queues/storage-queues-introduction), decodes them, and prints their content. It continuously polls the queue for new messages every 10 seconds.

## Prerequisites

- [Python 3.6 or higher](https://www.python.org/downloads/)
- [Azure subscription](https://azure.microsoft.com/en-us/free/)
- [Azure Storage Account](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-overview)
- [Azure Queue Storage](https://docs.microsoft.com/en-us/azure/storage/queues/storage-queues-introduction)

## Installation

1. **Clone the repository:**

    ```sh
    git clone git@github.com:mjazwiecki/azure-storage-queue-reader.git
    cd read
    ```

2. **Create a virtual environment and activate it:**

    ```sh
    python3 -m venv .venv
    source .venv/bin/activate
    ```

3. **Install the required packages:**

    ```sh
    pip install -r requirements.txt
    ```

## Configuration

1. **Set up your Azure credentials:**

    Ensure you have the [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli) installed and logged in, or set up environment variables for Azure credentials.

2. **Create a `.env` file:**

    Create a `.env` file in the root directory and add the following variables:

    ```python
    AZURE_SUBSCRIPTION_ID = 'your_subscription_id'
    RESOURCE_GROUP = 'your_resource_group'
    AZURE_STORAGE_ACCOUNT = 'your_storage_account_name'
    QUEUE_NAME = 'your_queue_name'
    ```

## Usage

Run the script using the following command:

```sh
chmod +x ./read
./read
```
The script will continuously read messages from the specified Azure Storage Queue, decode them, and print their content.

## Functions
`read_message()`
Reads a single message from the storage queue, decodes it, prints its content, and deletes the message from the queue.

`decode_message(base64_message)`
Decodes a base64-encoded message.

`main()`
Continuously reads messages from the storage queue every 10 seconds.

## License
This project is licensed under the [MIT License](https://opensource.org/licenses/MIT). See the LICENSE file for details.

## Contributing
Contributions are welcome! Please open an issue or submit a pull request for any changes.

## Acknowledgements:
[Azure SDK for Python](https://github.com/Azure/azure-sdk-for-python)<br>
[Base64 Encoding](https://docs.python.org/3/library/base64.html)