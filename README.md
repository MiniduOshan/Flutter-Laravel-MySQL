# 🚀 Flutter + Laravel + MySQL Full Stack Project

A full-stack application built using Flutter (Frontend), Laravel (Backend API), and MySQL (Database), all managed within VS Code.

---

## 📌 Tech Stack

- Frontend: Flutter (Dart)
- Backend: Laravel (PHP)
- Database: MySQL
- Editor: VS Code

---

## 📁 Project Structure

my_project/
 ├── mobile_app/      # Flutter Application
 └── backend_api/     # Laravel API

---

## ⚙️ Prerequisites

Install:

- Flutter SDK
- VS Code
- Flutter Extension
- PHP
- Composer
- Laravel
- MySQL Server

---

## 📱 Flutter Setup

Create project:

    flutter create mobile_app
    cd mobile_app

Check setup:

    flutter doctor

Run app:

    flutter pub get
    flutter run

---

## 🖥️ Laravel Setup

Create project:

    composer create-project laravel/laravel backend_api
    cd backend_api

Run server:

    php artisan serve

API URL:
    http://127.0.0.1:8000

---

## 🗄️ MySQL Setup

Create database:

    CREATE DATABASE flutter_laravel_db;

---

## 🔗 Connect Laravel to MySQL

Edit .env:

    DB_CONNECTION=mysql
    DB_HOST=127.0.0.1
    DB_PORT=3306
    DB_DATABASE=flutter_laravel_db
    DB_USERNAME=root
    DB_PASSWORD=your_password

Run:

    php artisan config:clear
    php artisan migrate

---

## 🔌 API Setup

routes/api.php:

    Route::get('/test', function () {
        return response()->json([
            'message' => 'API working'
        ]);
    });

Test:
    http://127.0.0.1:8000/api/test

---

## 🔄 Connect Flutter to Laravel

Install package:

    flutter pub add http

Example:

    import 'dart:convert';
    import 'package:http/http.dart' as http;

    Future<void> fetchData() async {
      final response = await http.get(
        Uri.parse('http://10.0.2.2:8000/api/test'),
      );

      if (response.statusCode == 200) {
        final data = jsonDecode(response.body);
        print(data['message']);
      } else {
        print('Failed');
      }
    }

---

## 🌐 API URL Notes

- Android Emulator → http://10.0.2.2:8000  
- iOS Simulator → http://127.0.0.1:8000  
- Real Device → http://YOUR_LOCAL_IP:8000  

---

## ▶️ Daily Commands

Run backend:

    cd backend_api
    php artisan serve

Run frontend:

    cd mobile_app
    flutter run

---

## 🏗️ Architecture

Flutter App → Laravel API → MySQL Database

- Flutter = UI
- Laravel = API + logic
- MySQL = data storage

⚠️ Flutter should NOT connect directly to MySQL.

---

## ⚡ Quick Start

    flutter create mobile_app
    composer create-project laravel/laravel backend_api

    cd backend_api
    php artisan migrate
    php artisan serve

    cd mobile_app
    flutter run

---

## 📌 License

Open-source and free to use.

---

## 👨‍💻 Author

Minidu Oshan

Your Name
