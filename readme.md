CodeShop Warehouse
==================

In this checkpoint you are responsible for building out a warehouse management system. This warehouse needs to manage the stock of it's products through the use of Fill Orders. Fill Orders can be created ahead of when they are processed. There are two types of Fill Orders. One for adding stock, and one for removing stock from the product. Each Fill Order needs to be timestamped when it is Processed. Once a Fill Order is processed it should not be modified. If a mistake occurs a new Fill Order should be generated to correct the previous order. 

### Base Requirements
  - Application Layers must be separated into at least 4 Layers
    - Presentation
    - Entities
    - Business
    - Data
  - Application logic must be testable with a test layer
    - Manditory Tests
      - UnresolvedFillOrdersCanBeRetrieved
      - UnresolvedFillOrderCanBeProcessed
      - ProcessedFillOrderCannotBeModified
  - Application must have a Web Interface
    - See all open orders
    - Create an Order
    - Process an Order with 1 click
    - Processed orders do not have a button
    - See all orders by product Id


### Suggested Build Ideas

```csharp

  public interface IOrdersRepository
  {
    Order GetOrderById(int id);
    void UpdateOrder(Order o);
    Order CreateOrder(Order data);
    IEnumerable<Order> GetUnProcessedOrders();
    IEnumerable<Order> GetOrdersByProductId(int productId);
  }

  public class OrdersService
  {
    private readonly _ordersRepo;
    //...
  }

  public class OrderServiceTests
  {
    //Follow the 80/20 rule
    void UnresolvedFillOrdersCanBeRetrieved()
    {
      // Arrange
      // Act
      // Assert
    }
    void UnresolvedFillOrderCanBeProcessed(){}
    void ProcessedFillOrderCannontBeModified(){}
  }

```
