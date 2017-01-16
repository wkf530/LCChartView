# LCChartView
快速展示折线图, 柱状图

![LCChart.gif](https://github.com/Rochang/LCChartView/blob/master/LCChartView.gif)
# 使用说明
```obj
/* 初始化 */
LCAxisView *axisView = [LCAxisView getAxisViewLineWithYAxisMaxValue:1000];
LCAxisView *axisView1 = [LCAxisView getAxisViewBarWithYAxisMaxValue:1000];
LCAxisView *axisView2 = [[LCAxisView alloc] init];

/* 创建数据源 */
LCAxisViewDataModel *model = [LCAxisViewDataModel getModelWithChartColor:RandomColor plots:[self randomArrayWithCount:18]];
LCAxisViewDataModel *model1 = [LCAxisViewDataModel getModelWithChartColor:RandomColor plots:[self randomArrayWithCount:18]];
// 单组数据展示
axisView.dataSource = @[model];
// 多组数据展示
axisView1.dataSource = @[model, model1];

/* 开始绘画 */
[self.axisViewBar drawChartView];
```
# 自定义UI属性
文件LCAxisView.h中保留了一堆属性用于自定义UI,如需修改直接在drawChartView方法前设置即可实现.
```obj
// switch
@property (assign, nonatomic) BOOL showGridding;
@property (assign, nonatomic) BOOL showAnimation;
@property (assign, nonatomic) BOOL yShowPercent;
@property (assign, nonatomic) BOOL showPlotsLabel;
@property (assign, nonatomic) BOOL showPlotsLabelPersent;
@property (assign, nonatomic) BOOL PlotsLabelCanClick;
@property (assign, nonatomic) BOOL lineChartFillView;
@property (assign, nonatomic) LCChartViewType chartViewType;

// data
@property (copy, nonatomic) NSString *title;
@property (copy, nonatomic) NSString *xAxisTitle;
@property (copy, nonatomic) NSString *yAxisTitle;
@property (strong, nonatomic) NSArray <NSString *> *xAxisTitleArray;

// size
@property (assign, nonatomic) CGFloat yAxisMaxValue;
@property (assign, nonatomic) CGFloat axisWidth;
@property (assign, nonatomic, readonly) CGFloat xAxisTextMargin;
@property (assign, nonatomic) CGFloat yAxisToLeft;
@property (assign, nonatomic) NSInteger yAxisCount;
@property (assign, nonatomic) CGFloat topMargin;
@property (assign, nonatomic) CGFloat xTextToAxis;
@property (assign, nonatomic) CGFloat yTextToAxis;
@property (assign, nonatomic) CGFloat axisFontSize;
@property (assign, nonatomic) CGFloat plotsLabelFontSize;
@property (assign, nonatomic) CGFloat plotsButtonWH;
@property (assign, nonatomic) CGFloat lineChartWidth;
@property (assign, nonatomic) CGFloat chartViewRightMargin;
@property (assign, nonatomic) CGFloat displayPlotToLabel;
@property (assign, nonatomic) CGFloat barWidth;

// color
@property (strong, nonatomic) UIColor *backColor;
@property (strong, nonatomic) UIColor *yTextColor;
@property (strong, nonatomic) UIColor *xTextColor;
@property (strong, nonatomic) UIColor *axisColor;
@property (strong, nonatomic) UIColor *plotsLabelColor;
@property (strong, nonatomic) UIColor *plotsLabelSelectedColor;
@property (strong, nonatomic) UIColor *lineChartFillViewColor;

@property (strong, nonatomic) UIColor *plotsButtonColor;
@property (strong, nonatomic) UIColor *plotsButtonSelectedColor;
// 或者图片
@property (strong, nonatomic) NSString *plotsButtonImage;
@property (strong, nonatomic) NSString *plotsButtonSelectedImage;
```
# 实现思路
项目中只用了一对.h .m文件,为了增强阅读性,所有的方法已经细分.可以参考LCAxisView.m的mark.
```obj
#pragma mark - 开始描绘LCChartView
- (void)drawChartView {
}
#pragma mark - 重置数据
- (void)resetDataSource {
}
#pragma mark - 描绘Y轴
- (void)drawYAxis {
}
#pragma mark - 描绘X轴
- (void)drawXAxis {
}
#pragma mark - Y轴分割线
- (void)drawYSeparators {
}
#pragma mark - X轴分割线
- (void)drawXSeparators {
}
#pragma mark - 创建,显示数据label
- (void)drawDisplayLabels {
}
#pragma mark - 描绘ChartViewLine折线图
- (void)drawLineChartViewPots {
}
- (void)drawLineChartViewLines {
}
#pragma mark - ChartViewBar柱状图
- (void)drawBarChartViewBars {
}
```
