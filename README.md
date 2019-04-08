# datewrapper

`no.ivarref.DateIObj`: a class extending `java.util.Date` and implementing `IObj`.

## Installation

Add `[no.ivarref/datewrapper "0.1.0"]` to your dependencies.

## Code

```java
package no.ivarref;

import clojure.lang.IObj;
import clojure.lang.IPersistentMap;

import java.util.Date;

public class DateIObj extends Date implements IObj {

    private final IPersistentMap iPersistentMap;

    public DateIObj() {
        super();
        this.iPersistentMap = null;
    }

    public DateIObj(Date d) {
        super(d.getTime());
        this.iPersistentMap = null;
    }

    public DateIObj(Date d, IPersistentMap iPersistentMap) {
        super(d.getTime());
        this.iPersistentMap = iPersistentMap;
    }

    public IObj withMeta(IPersistentMap iPersistentMap) {
        return new DateIObj(new Date(this.getTime()), iPersistentMap);
    }

    public IPersistentMap meta() {
        return iPersistentMap;
    }
}
```