[Embedded && Embedable](#Embedded && Embedable)

## Embedded && Embedable
The @Embeddable annotation allows to specify a class whose instances are stored as intrinsic part of the owning entity.   
This annotation has no attributes.

```java
@Embeddable
public class EmploymentPeriod {
     java.util.Date startDate;
     java.util.Date endDate;
     ...
}
```   

The @Embedded annotation is used to specify a persistent field or property of an entity whose value is an instance of an embeddable class. By default, column definitions specified in the @Embeddable class apply to the table of the owning entity but you can override them using@AttributeOverride:

```java
@Embedded
@AttributeOverrides({
    @AttributeOverride(name="startDate", column=@Column(name="EMP_START")),
    @AttributeOverride(name="endDate", column=@Column(name="EMP_END"))
})
```
public EmploymentPeriod getEmploymentPeriod() { ... }   
Regarding the optional @Basic annotation, you may use it to configure the fetch type to LAZY and to configure the mapping to forbid null values (for non primitive types) with the optional attribute.
