# UIControl-SingleAction
<br/>
注：基于某位仁兄的demo修改的，原谅我不记得是哪位了。。。
<br>
直接拖进工程即可，防止暴力点击造成的事件重复提交
<br>
## 示例代码
<br/>
<pre>

#import "ViewController.h"
#import "UIControl+SingleAction.h"//如果要修改点击的时间间隔，请导入这个头文件，不单独修改可以不导入

@interface ViewController ()

@end

@implementation ViewController

- (void)viewDidLoad {
    [super viewDidLoad];
    
    UIButton *cusBtn=[UIButton buttonWithType:UIButtonTypeCustom];
    //单独修改某个button点击事件时间间隔，默认2秒
    cusBtn.cjr_acceptEventInterval=0.1;
    [self.view addSubview:cusBtn];
    cusBtn.frame=CGRectMake(100, 100, 100, 100);
    cusBtn.backgroundColor=[UIColor orangeColor];
    [cusBtn addTarget:self action:@selector(clickCusBtn:) forControlEvents:UIControlEventTouchUpInside];
}
-(void)clickCusBtn:(UIControl *)btn
{
    NSLog(@"clickCusBtn");
}

- (IBAction)btnClick:(UIButton *)sender {
    NSLog(@"btnClick");
}

@end
</pre>