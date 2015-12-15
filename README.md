# ObjC-TagView
View for displaying tag list

![portrait image](https://raw.githubusercontent.com/mokelab/ObjC-TagView/master/portrait.png)

![landscape image](https://raw.githubusercontent.com/mokelab/ObjC-TagView/master/landscape.png)

# How to use this

Copy `MLTagView.h` and `MLTagView.m` to your app project. This class is just a subclass of `UIView`

```
#import "MLTagView.h"

@interface ViewController : UIViewController

@property(weak, nonatomic) IBOutlet MLTagView *tagView;

@end

@implementation ViewController

- (void)viewDidLoad {
    [super viewDidLoad];
    // Do any additional setup after loading the view, typically from a nib.
    self.tagView.margin = 4;
    self.tagView.itemBorderWidth = 2;
    self.tagView.itemCornerRadius = 8;
    self.tagView.itemTitleColor = [UIColor grayColor];
    self.tagView.itemTitlePadding = 16;
    for (int i = 0 ; i < 30 ; ++i) {
        [self.tagView addTag:[NSString stringWithFormat:@"Tag %d", i]];
    }
}

@end
```

# for AutoLayout

Add `height` constraint to this View and connect it to `heightConstraint` property. This view updates `constant` of constraint after `layoutSubviews`
