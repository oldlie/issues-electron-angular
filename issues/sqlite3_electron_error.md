[问题记录](../README.md)


## Angular 测试时出现： ``` 'router-outlet' is not a known element: ``` 错误

需要在测试文件中添加导入声明：
```
import { RouterTestingModule } from "@angular/router/testing";

  beforeEach(async(() => {
    TestBed.configureTestingModule({
      imports: [
        RouterTestingModule,
      ],
      declarations: [
        AppComponent
      ],
    }).compileComponents();
  }));
```

参考文档： [ANGULAR COMPONENT TESTING WITH ROUTERLINK AND ROUTEROUTLET](http://www.kirjai.com/ng2-component-testing-routerlink-routeroutlet/ "router-outlet is not a konw element")

[问题记录](../README.md)