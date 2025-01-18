# WebGIS Project

A WebGIS (Web Geographic Information System) project that allows users to interact with maps, manage geospatial data, and perform CRUD (Create, Read, Update, Delete) operations with role-based access control.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Architecture](#architecture)
- [Setup and Deployment](#setup-and-deployment)
  - [Domain Configuration](#domain-configuration)
  - [Server Setup](#server-setup)
  - [Database Configuration](#database-configuration)
  - [SSL Configuration](#ssl-configuration)
  - [Application Setup](#application-setup)
- [Usage](#usage)
- [Technologies Used](#technologies-used)
- [Contributing](#contributing)
- [License](#license)

## Overview

This WebGIS project provides an interactive mapping platform where users can create, edit, and export point layers on a Leaflet map. It incorporates user authentication with role-based permissions, ensuring that students, teachers, and managers have appropriate access levels to perform CRUD operations on the map data.

## Features

- **User Authentication:** Secure login and registration system connected to a MySQL database.
- **Role-Based Access Control:** Assign roles (Student, Teacher, Manager) with specific permissions for CRUD operations.
- **Interactive Mapping:** Utilize Leaflet for creating and managing point layers.
- **Data Export:** Export map data in various formats.
- **Responsive Design:** Accessible on various devices and screen sizes.
- **Secure Connection:** HTTPS support with SSL certificates.

## Architecture

![Architecture Diagram](docs/architecture.png)

## Setup and Deployment

### Domain Configuration

1. **Domain Provider:** Natro
2. **DNS Configuration:**
   - Configured **A records** pointing to the Elastic IP.
   - Configured **CNAME records** for subdomains as needed.

### Server Setup

1. **AWS EC2 Instance:**
   - Instance Type: `t3.micro`
   - Created an Elastic IP and attached it to the EC2 instance for a stable IP address.

2. **Nginx Server:**
   - Installed and configured Nginx.
   - Attached the Elastic IP to the domain `barancicek.com.tr`.

### Database Configuration

1. **Amazon RDS:**
   - Created a MySQL database using Amazon RDS (Relational Database Service).
   - Configured security groups and inbound rules for database access.

2. **Inbound Rules:**
   - Edited inbound rules to allow HTTP and HTTPS traffic.

### SSL Configuration

1. **Certbot:**
   - Installed Certbot to manage SSL certificates.
   - Generated two SSL certificates:
     - `barancicek.com.tr`
     - `www.barancicek.com.tr`

### Application Setup

1. **Node.js Application:**
   - Initialized a Node.js project.
   - Built the project with necessary dependencies.

2. **Process Management:**
   - Used **PM2** to run the Node.js server continuously, ensuring uptime and automatic restarts.

## Usage

1. **Access the Application:**
   - Navigate to `https://barancicek.com.tr` or `https://www.barancicek.com.tr`.

2. **Authentication:**
   - Register a new account or log in with existing credentials.
   - Assign roles (Student, Teacher, Manager) via the MySQL database to control permissions.

3. **Map Interaction:**
   - Create point layers on the Leaflet map.
   - Edit existing points and layers as per assigned permissions.
   - Export map data for offline use or further analysis.

## Technologies Used

- **Frontend:**
  - Leaflet.js
  - HTML5, CSS3, JavaScript

- **Backend:**
  - Node.js
  - Express.js

- **Database:**
  - MySQL (Amazon RDS)

- **Server:**
  - Nginx
  - AWS EC2 (t3.micro)
  - PM2

- **Security:**
  - SSL Certificates via Certbot
  - HTTPS Configuration

- **Domain Management:**
  - Natro Domain Services

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes.

1. Fork the repository.
2. Create a new branch: `git checkout -b feature/YourFeature`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin feature/YourFeature`
5. Open a pull request.

## License

This project is licensed under the [MIT License](LICENSE).

