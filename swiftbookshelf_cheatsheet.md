# 🚕💨 SwiftBookshelf — шпаргалка

| ✅ Команда | 📝 Псевдокод | 🔥 Код | 🚨 Ошибка (что забыла) |
|------------|--------------|---------|------------------------|
| `new` | Запросить название, автора, год → создать книгу | `guard let title = readLine(), !title.isEmpty else { continue }`<br>`guard let year = Int(yearInput) else { continue }`<br>`let book = Book(...)`<br>`store.add(book: book)` | `guard` требует `continue`<br>забываю `Int()` для года |
| `list` | Показать все книги с номерами | `guard !bookshelf.isEmpty else { print("No books"); return }`<br>`for (index, book) in bookshelf.enumerated()`<br>`print("\(index + 1). \(book.title)")` | забываю `enumerated()`<br>путаю `index + 1` |
