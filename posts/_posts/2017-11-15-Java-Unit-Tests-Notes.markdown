---
title: Java Unit Tests Notes
description: unit,
---

# Mockito

### Mock a static method in a class

````java
PowerMockito.mockStatic(StaticFactory.class);

PowerMockito.when(StaticFactory.create("Client")).thenReturn(client);
````

### Mock a final class
In case you need a test with a mocked final class use annotations:

````java
import org.junit.runner.RunWith;
import org.powermock.modules.junit4.PowerMockRunner;
import org.powermock.core.classloader.annotations.PrepareForTest;

@RunWith(PowerMockRunner.class)
@PrepareForTest(FinalClass.class)
````



