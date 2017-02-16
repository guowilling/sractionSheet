# SRActionSheet

## Features

* There are two styles for other action items: only title, default alignment is left; title and image, default alignment is center.    
* You can custom alignment through otherActionItemAlignment property.

***

* 其它选择器项有两种样式: 只有标题时, 默认左对齐方式居左; 标题和图像时, 默认对齐方式居中.
* 您可以通过 otherActionItemAlignment 属性自定义对齐方式.

## Show

![image](./show1.jpg) ![image](./show2.jpg)  
  
***

![image](./show3.jpg) ![image](./show4.jpg)

### CocoaPods
> Add **pod ‘SRActionSheet’** to the Podfile, then run **pod install** in the terminal.

### Manual
> Drag the **SRActionSheet** folder to the project.

## Usage

````objc
// Only Title 
// Alignment left.
SRActionSheet *actionSheet = [[SRActionSheet alloc] initWithTitle:@"分享"
                                                      cancelTitle:@"取消"
                                                 destructiveTitle:nil
                                                      otherTitles:@[@"微信好友", @"微信朋友圈", @"QQ", @"QQ空间"]
                                                         delegate:self];
actionSheet.otherActionItemAlignment = SROtherActionItemAlignmentLeft;
[actionSheet show];         

// Alignment center which is default.
[SRActionSheet sr_showActionSheetViewWithTitle:@"分享"
                                   cancelTitle:@"取消"
                              destructiveTitle:nil
                                   otherTitles:@[@"微信好友", @"微信朋友圈", @"QQ", @"QQ空间"]
                                   otherImages:nil
                              selectSheetBlock:^(SRActionSheet *actionSheetView, NSInteger index) {
                                  NSLog(@"%zd", index);
                              }];                         
````

````objc
// Title And Image  
// Alignment left which is default.
[SRActionSheet sr_showActionSheetViewWithTitle:@"分享"
                                   cancelTitle:@"取消"
                              destructiveTitle:nil
                                   otherTitles:@[@"微信好友", @"微信朋友圈", @"QQ", @"QQ空间"]
                                   otherImages:@[[UIImage imageNamed:@"share_wx_friend"],
                                                 [UIImage imageNamed:@"share_wx_pengyouquan"],
                                                 [UIImage imageNamed:@"share_qq_friend"],
                                                 [UIImage imageNamed:@"share_qq_kongjian"]]
                              selectSheetBlock:^(SRActionSheet *actionSheetView, NSInteger index) {
                                  NSLog(@"%zd", index);
                              }];

// Alignment center.     
SRActionSheet *actionSheet = [[SRActionSheet alloc] initWithTitle:@"分享"
                                                      cancelTitle:@"取消"
                                                 destructiveTitle:nil
                                                      otherTitles:@[@"微信好友", @"微信朋友圈", @"QQ", @"QQ空间"]
                                                      otherImages:@[[UIImage imageNamed:@"share_wx_friend"],
                                                                    [UIImage imageNamed:@"share_wx_pengyouquan"],
                                                                    [UIImage imageNamed:@"share_qq_friend"],
                                                                    [UIImage imageNamed:@"share_qq_kongjian"]]
                                                         delegate:self];
actionSheet.otherActionItemAlignment = SROtherActionItemAlignmentCenter;
[actionSheet show];
````

## Custom

````objc
/**
 Default is SROtherActionItemAlignmentCenter when no images but when there are images default is SROtherActionItemAlignmentLeft.
 */
@property (nonatomic, assign) SROtherActionItemAlignment otherActionItemAlignment;
````

**If you have any question, submit an issue or contact me.**   
**If this repo helps you, please give it a star.**  
**Have Fun.**
