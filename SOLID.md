# SOLID Principles - Explained with Real-World Examples

## 1. **Single Responsibility Principle (SRP)**
**Definition:** A class should have one, and only one, reason to change.

**Real-World Example:**
A `ReportGenerator` class should not also handle report formatting or data access. Instead:

```csharp
public class ReportGenerator
{
    public string GenerateReport() => "Report Content";
}

public class ReportFormatter
{
    public string FormatToPdf(string content) => "PDF: " + content;
}
```

---

## 2. **Open/Closed Principle (OCP)**
**Definition:** Software entities should be open for extension but closed for modification.

**Real-World Example:**
Use polymorphism to support new file export formats without modifying existing code.

```csharp
public abstract class Exporter
{
    public abstract void Export(string data);
}

public class PdfExporter : Exporter
{
    public override void Export(string data) => Console.WriteLine("Exporting to PDF");
}
```

---

## 3. **Liskov Substitution Principle (LSP)**
**Definition:** Derived classes must be substitutable for their base classes without altering correctness.

**Violation Example:**
```csharp
public class User { public virtual void AccessDashboard() => Console.WriteLine("Access granted"); }
public class GuestUser : User { public override void AccessDashboard() => throw new UnauthorizedAccessException(); }
```

**Fix:**
```csharp
public abstract class User {
    public abstract bool CanAccessDashboard();
    public abstract void AccessDashboard();
}

public class GuestUser : User {
    public override bool CanAccessDashboard() => false;
    public override void AccessDashboard() => Console.WriteLine("Redirect to login");
}
```

---

## 4. **Interface Segregation Principle (ISP)**
**Definition:** Clients should not be forced to depend on interfaces they do not use.

**Violation Example:**
```csharp
public interface IMachine { void Print(); void Fax(); void Scan(); }
public class OldPrinter : IMachine {
    public void Print() {}
    public void Fax() => throw new NotImplementedException();
    public void Scan() => throw new NotImplementedException();
}
```

**Fix:**
```csharp
public interface IPrinter { void Print(); }
public interface IScanner { void Scan(); }
public interface IFax { void Fax(); }

public class OldPrinter : IPrinter {
    public void Print() { }
}
```

---

## 5. **Dependency Inversion Principle (DIP)**
**Definition:** High-level modules should not depend on low-level modules. Both should depend on abstractions.

**Real-World Example:**
```csharp
public interface IMessageSender {
    void SendMessage(string message);
}

public class EmailSender : IMessageSender {
    public void SendMessage(string message) => Console.WriteLine("Email: " + message);
}

public class NotificationService {
    private readonly IMessageSender _messageSender;
    public NotificationService(IMessageSender sender) => _messageSender = sender;
    public void Notify(string msg) => _messageSender.SendMessage(msg);
}
```

---

### ✅ Summary Table

| Principle | Responsibility |
|-----------|----------------|
| SRP       | One reason to change |
| OCP       | Extend without modify |
| LSP       | Subclass should behave like base |
| ISP       | Split fat interfaces |
| DIP       | Depend on abstractions |
