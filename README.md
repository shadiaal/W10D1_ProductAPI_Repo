
# ProductApi Project

This is a simple ASP.NET Core Web API that exposes the following endpoints:

## Endpoints

- **GET /api/products** - List all products.
- **GET /api/products/{id}** - Get a single product by ID.
- **POST /api/products** - Add a product.

## Features

- **In-memory product list**: The API uses an in-memory list to store product data.
- **Dependency Injection**: The application follows best practices with dependency injection and a service layer to manage business logic.
- **Configuration**: The application reads configuration settings like `AppName` and `DefaultCurrency` from the configuration.

## Setup Instructions

1. **Clone the repository**:
   ```bash
   git clone https://github.com/shadiaal/W10D1_ProductAPI_Repo.git
   cd W10D1_ProductAPI_Repo
   ```

2. **Install Dependencies**:
   Ensure you have the .NET SDK installed on your machine. You can check your installation with:
   ```bash
   dotnet --version
   ```

3. **Build the API**:
   To build the project, run the following command:
   ```bash
   dotnet build
   ```

4. **Run the API**:
   You can run the API with the following command:
   ```bash
   dotnet run
   ```

5. **Dockerize the API**:
   To containerize the application with Docker, follow these steps:
   - Build the Docker image:
     ```bash
     docker build -t productapi-img .
     ```
   - Run the Docker container:
     ```bash
     docker run -p 5001:8080 productapi
     ```

6. **Push the Docker image to Docker Hub**:
   - Log in to Docker Hub:
     ```bash
     docker login
     ```
   - Tag the image:
     ```bash
     docker tag productapi soosh131/productapi-img:latest
     ```
   - Push the image:
     ```bash
     docker push soosh131/productapi-img:latest
     ```

7. **Kubernetes Deployment**:
   Create Kubernetes manifests for deploying the application. The manifests should include a Deployment, Service, and Ingress resource.

   You can apply the manifests using kubectl:
   ```bash
   kubectl apply -f k8s/
   ```

8. **Access the app via Minikube**:
   - Run the Minikube service:
     ```bash
     minikube service productapi
     ```
   This will open the Product API in your browser.

## Configuration

The application reads the following configuration values:

- `AppName`: The name of the application.
- `DefaultCurrency`: The default currency for the product prices.

These values can be configured in the `appsettings.json` file or set in your environment.


