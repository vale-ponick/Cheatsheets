# 🚕💨 SwiftBookshelf — шпаргалка

| ✅ Команда | 📝 Псевдокод | 🔥 Код | 🚨 Ошибка (что забыла) |
|------------|--------------|---------|------------------------|
| `new` | Запросить название, автора, год → создать книгу | `guard let title = readLine(), !title.isEmpty else { continue }`<br>`guard let year = Int(yearInput) else { continue }`<br>`let book = Book(...)`<br>`store.add(book: book)` | `guard` требует `continue`<br>забываю `Int()` для года |
| `list` | Показать все книги с номерами | `guard !bookshelf.isEmpty else { print("No books"); return }`<br>`for (index, book) in bookshelf.enumerated()`<br>`print("\(index + 1). \(book.title)")` | забываю `enumerated()`<br>путаю `index + 1` |
| `view` | Запросить номер → показать книгу | `guard let num = Int(readLine()!) else { continue }`<br>`store.view(at: num - 1)` | `num - 1` |
| `delete` | Запросить номер → удалить книгу | `guard let num = Int(readLine()!) else { continue }`<br>`store.delete(at: num - 1)` | `num - 1` |
| `save` | Сохранить массив в JSON | `let encoder = JSONEncoder()`<br>`encoder.outputFormatting = .prettyPrinted`<br>`encoder.dateEncodingStrategy = .iso8601`<br>`guard let data = try? encoder.encode(bookshelf) else { return }`<br>`try? data.write(to: fileURL)` | забываю `.iso8601`<br>забываю `.prettyPrinted` |
| `load` | Загрузить массив из JSON | `guard FileManager.default.fileExists(atPath: fileURL.path) else { return }`<br>`guard let data = try? Data(contentsOf: fileURL) else { return }`<br>`let decoder = JSONDecoder()`<br>`decoder.dateDecodingStrategy = .iso8601`<br>`guard let loaded = try? decoder.decode([Book].self, from: data) else { return }`<br>`bookshelf = loaded` | забываю `.dateDecodingStrategy`<br>забываю `[Book].self` |
| `export` | Выгрузить в текстовый файл | `var result = ""`<br>`for (index, book) in bookshelf.enumerated() {`<br>&nbsp;&nbsp;`result += "\(index + 1). \(book.title)\n"`<br>`}`<br>`let textURL = fileURL.deletingLastPathComponent().appendingPathComponent("books.txt")`<br>`guard let data = result.data(using: .utf8) else { return }`<br>`try? data.write(to: textURL)` | забываю `\n`<br>путаю `appendingPathComponent` |
| `quit` | Сохранить и выйти | `store.save()`<br>`print("By, vale.ponick!")`<br>`return` | не забыть `save()` перед выходом |
