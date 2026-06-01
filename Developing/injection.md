## Spring Beans and Dependency Injection

- recommend using constructor injection to wire up depedencies and `@ComponentScan` to find beans.
- `@SpringBootApplication` implicitly includes `@ComponentScan`, all application components (`@Component`, `@Service`, `@Repository`, `@Controller` and others) are automatically registered as beans.
- eg: `@Service` bean that uses constructor injection to obtain a required `RiskAssessor` bean:
    ```java
    @Service
    public class MyAccountService implements AccountServiece{
      private final RiskAssessor riskAssessor;

      public MyAccountService(RiskAssessor riskAssessor){
        this.riskAssessor = riskAssessor;
      }
    }
    ```
- if a bean has more than one constructor, you will need to mark the one you want spring to use with `@Autowired`:
```java
  import java.io.PrintStream;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;

@Service
public class MyAccountService implements AccountService {

	private final RiskAssessor riskAssessor;

	private final PrintStream out;

	@Autowired
	public MyAccountService(RiskAssessor riskAssessor) {
		this.riskAssessor = riskAssessor;
		this.out = System.out;
	}

	public MyAccountService(RiskAssessor riskAssessor, PrintStream out) {
		this.riskAssessor = riskAssessor;
		this.out = out;
	}

	// ...

}
  ```
Tip: ```using constructor injection lets the riskAssessor field be marked as final, indicating that it cannot be changed subsequently.```
