1. Create a Database Library.

use Library

2. Create a collection named books.

db.createCollection("books")

3. Insert some sample documents into the ‘books’ collection.

db.books.insertMany([
    {
        "title": "Pride and Prejudice",
        "author": "Jane Austen",
        "year_published": 1813,
        "genres": ["Fiction", "Romance"],
        "available": true
    },
    {
        "title": "The Catcher in the Rye",
        "author": "J.D. Salinger",
        "year_published": 1951,
        "genres": ["Fiction", "Classic"],
        "available": true
    },
    {
        "title": "The Hobbit",
        "author": "J.R.R. Tolkien",
        "year_published": 1937,
        "genres": ["Fantasy", "Adventure"],
        "available": true
    },
    {
        "title": "Moby-Dick",
        "author": "Herman Melville",
        "year_published": 1851,
        "genres": ["Fiction", "Adventure"],
        "available": true
    },
    {
        "title": "War and Peace",
        "author": "Leo Tolstoy",
        "year_published": 1869,
        "genres": ["Historical Fiction", "Classic"],
        "available": true
    },
    {
        "title": "The Odyssey",
        "author": "Homer",
        "year_published": -800,
        "genres": ["Epic", "Adventure"],
        "available": true
    },
    {
        "title": "The Brothers Karamazov",
        "author": "Fyodor Dostoevsky",
        "year_published": 1880,
        "genres": ["Fiction", "Philosophical"],
        "available": true
    },
    {
        "title": "Brave New World",
        "author": "Aldous Huxley",
        "year_published": 1932,
        "genres": ["Dystopian", "Science Fiction"],
        "available": true
    },
    {
        "title": "The Divine Comedy",
        "author": "Dante Alighieri",
        "year_published": 1320,
        "genres": ["Epic", "Poetry"],
        "available": true
    },
    {
        "title": "Crime and Punishment",
        "author": "Fyodor Dostoevsky",
        "year_published": 1866,
        "genres": ["Fiction", "Philosophical"],
        "available": true
    }
])

![Screenshot 2025-05-08 084843](https://github.com/user-attachments/assets/5299756f-1363-4da1-b051-6004d24db7ab)
![Screenshot 2025-05-08 084859](https://github.com/user-attachments/assets/9479b9ff-15e3-4817-9d30-4f826bc1fdd8)
![Screenshot 2025-05-08 084919](https://github.com/user-attachments/assets/273261ac-6e2b-472b-bb01-8c8bf8097f9f)
![Screenshot 2025-05-08 084952](https://github.com/user-attachments/assets/15cac411-6b2b-4650-950a-4d87c58e7366)

4. Find all documents in the ‘books’ collection.

db.books.find()

![Screenshot 2025-05-08 084655](https://github.com/user-attachments/assets/a5f641a4-6c8c-4919-afde-089ab3e7b7d9)
![Screenshot 2025-05-08 084712](https://github.com/user-attachments/assets/a293480e-15d0-4f45-ae8e-f5e606a72270)
![Screenshot 2025-05-08 084727](https://github.com/user-attachments/assets/d63c4f0e-853c-492c-94f3-6dfc75a1562a)
![Screenshot 2025-05-08 084741](https://github.com/user-attachments/assets/1f2b5f63-ddca-404e-bd52-28edabc44b94)
![Screenshot 2025-05-08 084755](https://github.com/user-attachments/assets/cf3112df-70a6-43e2-a00d-14f77755f4f4)

5. Find books published after 1950.

db.books.find({ year_published: { $gt: 1950 } })

![Screenshot 2025-05-08 084625](https://github.com/user-attachments/assets/9de10cf2-d995-4ad6-8f24-daf7a9fb8fd4)
 
6. Find a book by title.

db.books.findOne({ title: "The Great Gatsby" })

![Screenshot 2025-05-08 084613](https://github.com/user-attachments/assets/24320d29-3030-4432-a872-edb26c66464b)

7. Update the year published for "The Great Gatsby".

db.books.updateOne(
  { title: "The Great Gatsby" },
  { $set: { year_published: 1925 } }
)

![Screenshot 2025-05-08 084600](https://github.com/user-attachments/assets/6908537c-d44f-4def-b05d-a88f188b5c2b)

8. Update the available status of "Moby-Dick" to false.

db.books.updateOne(
  { title: "Moby-Dick" },
  { $set: { available: false } }
)

![Screenshot 2025-05-08 084534](https://github.com/user-attachments/assets/aa8c7a5d-ddb6-4b47-ac7d-19c8810e4b7c)
 
9. Set a new field checked_out to false for all available books.

db.books.updateMany(
  { available: true },
  { $set: { checked_out: false } }
)

![Screenshot 2025-05-08 084521](https://github.com/user-attachments/assets/93243ea9-9978-4f9f-bd77-7a37503bf835)

10. Change the checked_out status to true for books in the "Adventure" genre.

db.books.updateMany(
  { genres: "Adventure" },
  { $set: { checked_out: true } }
)

![Screenshot 2025-05-08 084504](https://github.com/user-attachments/assets/1adec75e-2203-4b85-bc44-763d7673e45f)

11. Delete a book by title.

db.books.deleteOne({ title: "The Odyssey" })

![Screenshot 2025-05-08 084448](https://github.com/user-attachments/assets/bf054a04-a2df-434b-80f8-b947b1e8d7c8)

12. Delete all books published before 1930.

db.books.deleteMany({ year_published: { $lt: 1930 } })

![Screenshot 2025-05-08 084318](https://github.com/user-attachments/assets/5d38d2ad-dc1a-4d06-86a7-967cac163a2c)
