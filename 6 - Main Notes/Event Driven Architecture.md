2025-09-13 19:25

Status: #new 

Tags: [[Java]]

# Event Driven Architecture
Event Driven Architecture is a software design pattern where components communicate by producing and consuming events. Instead of directly calling methods on each other (tight coupling), components remain loosely coupled and react to "events" that occur.
- Event
	- A record of something that happened (e.g. UserCreated, OrderPlaced, Payment Processed)
	- A change in state
- Event Producer
	- Component that generates events
- Event Bus/Broker
	- Channel that delivers events from producers to consumers (can be in-memory or external, like Kafka or RabbitMQ)
- Event Consumer (Listener)
	- Component that reacts to an event
![[Main components of EDA.png]]

### Workflow
1. Something happens -> an event is created (`OrderPlacedEvent`)
2. The event producer publishes this event to an event broker
3. The event consumers (listeners/handlers) subscribed to that event receive it and take action
4. Multiple consumers can independently react to the same event.

## ✅ Simple Example in Java

### 1. Define an Event
```
public class OrderPlacedEvent {
    private final String orderId;

    public OrderPlacedEvent(String orderId) {
        this.orderId = orderId;
    }

    public String getOrderId() {
        return orderId;
    }
}
```
### 2. Define an Event Listener Interface

```
public interface EventListener<T> {
    void onEvent(T event);
}
```

### 3. Create an Event Bus (Simple In-Memory)

```
import java.util.ArrayList;
import java.util.List;

public class EventBus {
    private final List<EventListener<?>> listeners = new ArrayList<>();

    public <T> void register(EventListener<T> listener) {
        listeners.add(listener);
    }

    public <T> void publish(T event) {
        for (EventListener<?> listener : listeners) {
            if (listener instanceof EventListener<?>) {
                ((EventListener<T>) listener).onEvent(event);
            }
        }
    }
}
```

### 4. Implement Consumers

```
public class EmailNotificationService implements EventListener<OrderPlacedEvent> {
    @Override
    public void onEvent(OrderPlacedEvent event) {
        System.out.println("📧 Sending email for order: " + event.getOrderId());
    }
}

public class InventoryService implements EventListener<OrderPlacedEvent> {
    @Override
    public void onEvent(OrderPlacedEvent event) {
        System.out.println("📦 Reducing stock for order: " + event.getOrderId());
    }
}
```

### 5. Putting It Together

```
public class Main {
    public static void main(String[] args) {
        EventBus eventBus = new EventBus();

        // Register consumers
        eventBus.register(new EmailNotificationService());
        eventBus.register(new InventoryService());

        // Produce event
        OrderPlacedEvent event = new OrderPlacedEvent("ORD123");
        eventBus.publish(event);
    }
}
```

### ▶️ Output

```
📧 Sending email for order: ORD123
📦 Reducing stock for order: ORD123
```
### Main Benefits
- The Decoupling of the producers and consumers
- The Scalability
- Flexibility
- Asynchronous processing
- A method to develop enterprise IT systems that allows info to flow in real time between applications, microservices, and connected devices as events occur throughout the business.
- EDA pushes info as events happen, which is better then waiting for systems to periodically poll for updates, as in the case with the API-led approach most companies take

### Use Cases
- Integrating applications
- Sharing and democratizing data across applications
- Connecting IoT devices for data ingestion and analytics
- Event-enabling microservices

### Practical Example: Retail & eCommerce
![[EDA Example Retail & eCommerce.png]]

# References
[The Complete Guide to Event-Driven Architecture](https://medium.com/@seetharamugn/the-complete-guide-to-event-driven-architecture-b25226594227)
