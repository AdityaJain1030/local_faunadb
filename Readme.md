# Local Fauna DB Setup

[FaunaDB](https://fauna.com/) local configuration, which also lets you access the dashoard at http://localhost:5000

## Prerequisites

[Docker and Docker Compose](https://www.docker.com/)

[NodeJS](https://nodejs.org/) (needed for the FaunaDB CLI tool)

Install the [FaunaDB CLI](https://github.com/fauna/fauna-shell) tool from <https://github.com/fauna/fauna-shell>

## Usage

### **Example usage**

In your terminal, enter the following commands

```bash
git clone https://github.com/AdityaJain1030/local_faunadb
docker-compose up -d
npm install -g fauna-shell

# fauna-cli stuff
fauna add-endpoint http://localhost:8443/ --alias localhost --key secret
fauna create-database YOUR_DB_NAME --endpoint=localhost
fauna create-key YOUR_DB_NAME --endpoint=localhost
# this should now log your faunaDB access key. Make note of this, and store this key somewhere safe
```

Navigate to http://localhost:5000. Enter http://localhost:8443 as the `Endpoint URL` and your secret key from the previous step as `Key Secret`.

![Dashboard Screenshot](https://github.com/AdityaJain1030/local_faunadb/blob/master/images/Dashboard_Screenshot.png)

From there you should be able to access the FaunaDB dasboard.

### **Usage in Code**

The proccess of connecting your local faunaDB instance to your project is a little different than connecting to one in the cloud. In your code, add these properties to your fauna client init.

```json
{
    "secret": "YOUR_SECRET_HERE",
    "scheme": "http",
    "domain": "127.0.0.1", //localhost
    "port": 8443
}
```

## Further Reading

[FaunaDB documentation](https://docs.fauna.com/fauna/current/index.html)
