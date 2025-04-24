# 📦 ProductController

Контроллер `ProductController` отвечает за операции с товарами, включая получение информации о товаре по идентификатору и добавление нового товара в базу данных.

---

## 🧱 Описание класса

```php
/**
 * Класс ProductController отвечает за операции с товарами.
 */
class ProductController {
    // Методы описаны ниже
}
```

---

## 🧩 Методы

### 🟢 getProductById

**Описание:**  
Метод `getProductById` возвращает информацию о товаре по его уникальному идентификатору.

**Сигнатура:**

```php
public function getProductById(int $id): ?array
```

| Параметр | Тип  | Обязательный | Описание                 |
|----------|------|--------------|--------------------------|
| `$id`    | int  | Да           | Уникальный идентификатор товара |

**Возвращает:**  
`array|null` — Ассоциативный массив с данными товара, если найден, или `null`, если товар не найден.

**Пример использования:**

```php
$product = $productController->getProductById(5);
```

---

### 🟡 addProduct

**Описание:**  
Метод `addProduct` добавляет новый товар в базу данных, используя переданные параметры.

**Сигнатура:**

```php
public function addProduct(string $name, float $price, int $storeId): bool
```

| Параметр | Тип    | Обязательный | Описание               |
|----------|--------|--------------|------------------------|
| `$name`  | string | Да           | Название товара        |
| `$price` | float  | Да           | Цена товара            |
| `$storeId` | int  | Да           | Идентификатор магазина |

**Возвращает:**  
`bool` — `true`, если товар был успешно добавлен, иначе `false`.

**Пример использования:**

```php
$success = $productController->addProduct("Ноутбук", 59999.99, 3);
```

---

## 🧩 Пример реализации класса

```php
class ProductController {
    public function getProductById(int $id): ?array {
        return $this->productModel->find($id);
    }

    public function addProduct(string $name, float $price, int $storeId): bool {
        return $this->productModel->create([
            'name' => $name,
            'price' => $price,
            'store_id' => $storeId
        ]);
    }
}
```
