import java.util.Arrays;
import java.util.Comparator;

class Product {
    int productId;
    String productName;
    String category;

    public Product(int id, String name, String category) {
        this.productId = id;
        this.productName = name;
        this.category = category;
    }

    @Override
    public String toString() {
        return "[" + productId + "] " + productName + " (" + category + ")";
    }
}

public class Main {

    public static Product linearSearch(Product[] products, String targetName) {
        for (Product product : products) {
            if (product.productName.equalsIgnoreCase(targetName)) {
                return product;
            }
        }
        return null;
    }

    public static Product binarySearch(Product[] products, String targetName) {
        int left = 0, right = products.length - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            int cmp = targetName.compareToIgnoreCase(products[mid].productName);
            if (cmp == 0) {
                return products[mid];
            } else if (cmp < 0) {
                right = mid - 1;
            } else {
                left = mid + 1;
            }
        }
        return null;
    }

    public static void main(String[] args) {
        Product[] products = {
            new Product(1, "Laptop", "Electronics"),
            new Product(2, "Shoes", "Footwear"),
            new Product(3, "Book", "Education"),
            new Product(4, "Phone", "Electronics"),
            new Product(5, "Bag", "Accessories")
        };

        System.out.println("Linear Search Result:");
        Product result1 = linearSearch(products, "Phone");
        System.out.println(result1 != null ? result1 : "Product not found.");

        Arrays.sort(products, Comparator.comparing(p -> p.productName.toLowerCase()));

        System.out.println("\nBinary Search Result:");
        Product result2 = binarySearch(products, "Phone");
        System.out.println(result2 != null ? result2 : "Product not found.");
    }
}
