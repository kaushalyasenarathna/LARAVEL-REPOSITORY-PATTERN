# Laravel Repository Pattern

This repository demonstrates the use of the Repository Pattern in a Laravel application. The Repository Pattern is a design concept that separates the data access logic from the rest of the application, promoting a clean and organized structure. In this case, it's applied to manage database operations related to orders.

## Getting Started

Follow these steps to set up the project on your local environment.

### Prerequisites

- PHP and Composer installed on your system.
- A database (e.g., MySQL) with appropriate credentials.

### Installation

1. Clone the repository to your local machine using Git:

   ```bash
   git clone https://github.com/kaushalyasenarathna/LARAVEL-REPOSITORY-PATTERN.git
   ```

2. Navigate to the project directory:

   ```bash
   cd LARAVEL-REPOSITORY-PATTERN
   ```

3. Install Composer dependencies:

   ```bash
   composer install
   ```

4. Create a `.env` file by copying the provided example:

   ```bash
   cp .env.example .env
   ```

5. Generate an application key:

   ```bash
   php artisan key:generate
   ```

6. Run database migrations and seed the database:

   ```bash
   php artisan migrate --seed
   ```

## Repository Pattern Overview

### Service Providers

In the `config/app.php` file, we've registered the `RepositoryServiceProvider` to enable dependency injection of the `OrderRepositoryInterface` throughout the application.

```php
'providers' => [
    // ...
    App\Providers\RepositoryServiceProvider::class,
    // ...
],
```

### Repository Service Provider

Inside the `App\Providers\RepositoryServiceProvider` class, the `OrderRepositoryInterface` is bound to the `OrderRepository` class in the `register` method. This binding allows for seamless use of the repository in various parts of the application.

### OrderRepository

The `OrderRepository` class located in the `App\Repositories` namespace implements the `OrderRepositoryInterface`. It provides methods to interact with the `Order` model, including operations like fetching all orders, retrieving orders by ID, creating, updating, and deleting orders.

### OrderController

The `OrderController`, found in the `App\Http\Controllers` namespace, handles HTTP requests related to orders. It utilizes the `OrderRepositoryInterface` for data access and responds by providing JSON data.

- `index`: Retrieves a list of all orders.
- `store`: Creates a new order.
- `show`: Retrieves an order by its ID.
- `update`: Updates an existing order.
- `destroy`: Deletes an order.

## Usage

You can use this repository as a foundation for your Laravel project that follows the Repository Pattern. Clone the repository, configure your environment, and adapt it to meet your specific project requirements.

Feel free to explore the code and customize it according to your needs.

 
