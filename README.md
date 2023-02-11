# Laravel Unit and Security Tests Workflow
This workflow uses GitHub Actions to automate the testing process and check for potential security vulnerabilities in your Laravel application.

## Step 1: Checkout Code
Checkout the code from the repository.

## Step 2: Setup PHP 8.1
Use the "Setup PHP 8.1" step with the shivammathur/setup-php@v2 action to install and configure PHP 8.1 on the virtual machine.

## Step 3: Restore Composer Cache
Use the actions/cache@v2 action to restore the composer cache, which speeds up the installation process.

## Step 4: Install Dependencies
Run the composer install command to download and install the required packages.

## Step 5: Setup Application
Run several PHP commands to copy the .env.example file to .env, generate an application key, and set the directory permissions.

## Step 6: Save Composer Cache
Use the actions/cache@v2 action to save the composer cache for future runs.

## Step 7: Execute Tests (Unit and Feature Tests)
Run the tests using the vendor/bin/phpunit command.

## Step 8: Code Check using PHPCS
Run a code check using PHPCS with the composer run test command.

## Step 9: Install Package Security Checker
Install the Package Security Checker with the composer require --dev enlightn/laravel-security-checker command.

## Step 10: Run Security Check
Run the security check using the php artisan security:check command.
