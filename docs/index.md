/**
 * Класс ProductController отвечает за операции с товарами.
 */
class ProductController {
    /**
     * Получить товар по идентификатору.
     *
     * @param int $id Идентификатор товара
     * @return array|null Массив с данными товара или null, если не найден
     */
    public function getProductById(int $id): ?array {
        return $this->productModel->find($id);
    }

    /**
     * Добавить новый товар.
     *
     * @param string $name Название товара
     * @param float $price Цена товара
     * @param int $storeId Идентификатор магазина
     * @return bool true при успешном добавлении, false — в противном случае
     */
    public function addProduct(string $name, float $price, int $storeId): bool {
        return $this->productModel->create([
            'name' => $name,
            'price' => $price,
            'store_id' => $storeId
        ]);
    }
}
