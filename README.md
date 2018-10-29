# TLTransitions
快速实现控制器/View的Present，并支持自定义动画

### V 1.0.0
#### API与使用
```objc
/**
 * 转场形式显示popView
 * 自适应位置
 * ⚠️调用该方法时，请先设定好popView的frame/bounds/Size
 *
 * @param popView 要显示的View
 * @param pType 显示类型
 * @return 返回转场代理TLPopTransition对象
 */
+ (instancetype)showView:(UIView *)popView popType:(TLPopType)pType;
```
1. 支持将一个View以Alert弹框的形式显示到屏幕中间（可以支持键盘监听）
```objc
CGRect bounds = CGRectMake(0, 0, self.view.bounds.size.width * 0.8f, 200.f);
TLTransition showView:[self creatViewWithBounds:bounds color:tl_Color(248, 218, 200)]
                   popType:TLPopTypeAlert];
```

2. 支持将一个View以ActionSheet底部弹框的形式显示到屏幕底部
```objc
CGRect bounds = CGRectMake(0, 0, self.view.bounds.size.width, 240.f);
[TLTransition showView:[self creatViewWithBounds:bounds color:tl_Color(218, 248, 120)]
                   popType:TLPopTypeActionSheet];
```