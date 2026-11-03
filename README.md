# Azure-WebApp-Deployment-

#Created a Schema webapp_details
-- Create Products Table
CREATE TABLE webapp_details.Products (
    ProductID INT IDENTITY(1,1) PRIMARY KEY,
    Name NVARCHAR(150) NOT NULL,
    Description NVARCHAR(MAX) NULL,
    Price DECIMAL(10, 2) NOT NULL,
    StockQuantity INT NOT NULL DEFAULT 0,
    ImageUrl NVARCHAR(500) NOT NULL,
    CreatedAt DATETIME2 DEFAULT SYSUTCDATETIME()
);


-- Create Orders Table


CREATE TABLE webapp_details.Orders (
    OrderID INT IDENTITY(1,1) PRIMARY KEY,
    CustomerName NVARCHAR(100) NOT NULL,
    CustomerEmail NVARCHAR(100) NOT NULL,
    TotalAmount DECIMAL(10, 2) NOT NULL,
    Status NVARCHAR(50) DEFAULT 'Processing',
    CreatedAt DATETIME2 DEFAULT SYSUTCDATETIME()
);


-- Seed Sample Catalog (Replace <storage-account> with your actual Azure Blob account name)


INSERT INTO webapp_details.Products (Name, Description, Price, StockQuantity, ImageUrl)
VALUES 
('Wireless ANC Headphones', 'High fidelity sound with hybrid ANC.', 4999.00, 30, 'https://<storage-account>.blob.core.windows.net/products/headphones.jpg'),
('Smart Fitness Band', 'AMOLED display with continuous heart tracking.', 2499.00, 50, 'https://<storage-account>.blob.core.windows.net/products/smartband.jpg'),
('Mechanical Keyboard', 'Compact 75% hot-swappable mechanical switches.', 3499.00, 20, 'https://<storage-account>.blob.core.windows.net/products/keyboard.jpg');


