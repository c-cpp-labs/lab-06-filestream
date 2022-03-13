# Лабораторная работа 7

## Теоретическая часть
Ознакомьтесь с циклом статей https://metanit.com/cpp/tutorial/8.2.php и https://metanit.com/cpp/tutorial/8.3.php


### Инструкция
Каждое задание должно быть выполнено в отдельном `.cpp` файле.
Прототипы функции должны быть вынесены в `header.hpp` файл.
Все `.cpp` файлы добавить в `CMakeLists.txt`

### Задание 1
* Реализуйте функцию сохранения массива слов в файл
```cpp
void save_to_file(const char* filename, const char** data, size_t size);
```

* Реализуйте функцию загрузки массива слов из файла
```cpp
void load_from_file(const char* filename, char** out_data, size_t& size);
```

### Задание 2
Есть структура `book`
```cpp
struct book
{
    char* author;
    char* title;
    int year;
};
```

* Реализуйте функцию сохранения массива книг в файл
```cpp
void save_to_file(const char* filename, const book* data, size_t size);
```

* Реализуйте функцию загрузки массива книг из файла
```cpp
void load_from_file(const std::string& filename, book* outData, size_t& size);
```

### Задание 3
Есть структура `student`. Читаем про [enum](http://cppstudio.com/post/8106/)
```cpp
enum score
{
    unsatisfactorily = 2,
    satisfactorily = 3,
    good = 4,
    excellent = 5
};

struct record {
    char* subject;
    score score;
};

struct record_book {
    record* records;
    size_t size;
};

struct student
{
    char* name;
    int year;
    record_book record_book;
};

struct group {
    char* name;
    student* students;
    size_t size;
};

struct groups {
    group* groups;
    size_t size;
};
```

* Реализуйте функцию сохранения группы в файл
```cpp
void save_to_file(const char* filename, const groups& groups);
```

* Реализуйте функцию загрузки группы из файла
```cpp
void load_from_file(const char* filename, const groups& out_groups);
```

* (Задание со звёздочкой) Реализуйте загрузку групп в формат `.csv` [про csv](https://ru.wikipedia.org/wiki/CSV) или `.tsv` [про tsv](https://ru.wikipedia.org/wiki/TSV)