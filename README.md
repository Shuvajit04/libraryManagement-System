
📚 Library Management System
The Library Management System is a database-driven project developed to manage the operations of a digital library efficiently. The primary objective of this system is to store and organize information about books, authors, library members, and the tracking of borrowed and overdue books. This system ensures that book loans are properly monitored and overdue notifications are triggered when necessary. The system is built using relational database tools such as PostgreSQL (or alternatively MySQL) and is managed through a user-friendly interface like pgAdmin or MySQL Workbench.

The database schema consists of five main entities: Books, Authors, Members, BookAuthors, and Loans. The Books table stores details about each book, including the title, genre, published year, and the number of available copies. The Authors table holds information about authors, such as their name and birth year. Since a book can have multiple authors and an author can write multiple books, a many-to-many relationship is established through a bridge table called BookAuthors, which connects the Books and Authors tables using foreign keys.

The Members table contains data about individuals who are registered with the library, including their name, email address, and the date they joined. The Loans table is used to track which member borrowed which book, the date of the loan, the due date, and the return date. It connects both the Members and Books tables via foreign keys, thus allowing the system to maintain a log of lending activity.

To enhance the functionality of the system, two important views have been created. The first view, called BorrowedBooks, lists all books that are currently borrowed by members and not yet returned. The second view, OverdueBooks, identifies all loans that are past their due dates and have not been returned, allowing the library to easily track and address overdue items.

A key feature of this system is the implementation of a trigger that automatically checks whether a new or updated loan has a due date that has already passed. If it does, the system raises a notification or error. In MySQL, this is implemented using the AFTER INSERT or AFTER UPDATE trigger along with the SIGNAL SQLSTATE clause, which raises a user-defined error if the due date is already overdue at the time of insertion or update.

The system also includes several reports for analytical purposes. One report displays the most active library members based on the number of loans they have made. Another report highlights the most popular books based on how frequently they have been borrowed. These insights help library staff make data-informed decisions about inventory, purchases, and member engagement.

The complete deliverables of the project include the Entity-Relationship Diagram (ERD), which visually represents all the entities and their relationships; the SQL dump containing the full schema and test data; the views and trigger scripts that automate and monitor borrowing activities; and this documentation, which explains the design, implementation, and purpose of each component in detail.

In the future, this system can be enhanced by adding features such as automated email or SMS notifications for overdue books, late fee calculations, reservation systems for books, borrowing limits for members, and even a graphical web-based or mobile interface for end-users. These upgrades would further improve the efficiency and accessibility of the library system.

