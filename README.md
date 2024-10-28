# PHP Book Library Management Task

## Task Description
Create a simple book library management system that allows users to perform basic CRUD operations (Create, Read, Update, Delete) on books using PHP and MySQL.

## Requirements

### Database Structure
Create a table named `books` with the following fields:
- id (INT, auto-increment, primary key)
- title (VARCHAR(255))
- author (VARCHAR(255))
- publication_year (INT)
- isbn (VARCHAR(13))
- available (BOOLEAN)
- created_at (TIMESTAMP)

### Features to Implement
1. Display all books in a table format with pagination (10 books per page)
2. Add a new book with form validation:
   - Title and author cannot be empty
   - Publication year must be between 1900 and current year
   - ISBN must be exactly 13 digits
   - Available status must be true/false
3. Edit existing book details
4. Delete a book with confirmation
5. Search functionality:
   - Search by title
   - Search by author
   - Filter by availability

### Technical Requirements
1. Use PHP PDO for database connections
2. Implement proper error handling
3. Use prepared statements for all database queries
4. Create reusable functions for common operations
5. Implement basic XSS protection
6. Use GET parameters for pagination and search
7. Use POST for create/update/delete operations

## Database Connection Template
```php
<?php
function getDatabaseConnection() {
    try {
        $host = 'localhost';
        $dbname = 'library';
        $username = 'root';
        $password = '';
        
        $pdo = new PDO("mysql:host=$host;dbname=$dbname", $username, $password);
        $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
        return $pdo;
    } catch(PDOException $e) {
        die("Connection failed: " . $e->getMessage());
    }
}
?>
```

## Sample Functions to Implement
```php
// Get all books with pagination
function getBooks($page = 1, $perPage = 10) {
    // TODO: Implement pagination logic
}

// Add new book
function addBook($title, $author, $year, $isbn, $available) {
    // TODO: Implement validation and insertion
}

// Update existing book
function updateBook($id, $title, $author, $year, $isbn, $available) {
    // TODO: Implement validation and update
}

// Delete book
function deleteBook($id) {
    // TODO: Implement deletion with validation
}

// Search books
function searchBooks($searchTerm, $searchBy = 'title') {
    // TODO: Implement search logic
}
```

## Evaluation Criteria
1. Code organization and structure
2. Proper input validation and error handling
3. SQL injection prevention
4. XSS protection implementation
5. Code reusability
6. User interface usability
7. Search and pagination functionality
8. Proper use of PHP PDO
9. Clean and well-documented code

## Bonus Points
1. Add user authentication
2. Implement book categories
3. Add book cover image upload functionality
4. Create an API endpoint for the operations
5. Add unit tests
6. Implement logging system

## Tips
- Start by creating the database and table structure
- Implement one feature at a time
- Test thoroughly after implementing each feature
- Pay attention to security best practices
- Document your code as you write it
- Handle edge cases appropriately
