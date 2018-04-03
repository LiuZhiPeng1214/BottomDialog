# BottomDialog
BottomDialog 一个自定义的从底部弹出的dialog，仿照微博的分享弹框

# 效果图 
![Alt text](/art/horizontal.png) ![Alt text](/art/vertical.png)

# 导入
   	dependencies {
	        compile 'com.github.LiuZhiPeng1214:BottomDialog:v1.0'
	}

# 使用
BottomDialog 只需要一句代码即可轻松显示底部弹框

## 创建Menu
    <?xml version="1.0" encoding="utf-8"?>
    <menu xmlns:android="http://schemas.android.com/apk/res/android">
        <item
            android:id="@+id/moments"
            android:icon="@mipmap/ic_share_moments"
            android:title="@string/moments" />
    </menu>
    
## 设置 Layout 样式
```
    new BottomDialog(MainActivity.this)
        .title(R.string.title_item)             //设置标题
        .layout(BottomDialog.GRID)              //设置内容layout,默认为线性(LinearLayout)
        .orientation(BottomDialog.VERTICAL)     //设置滑动方向,默认为横向
        .inflateMenu(R.menu.menu_share)         //传人菜单内容
        .background(R.color.white)              //设置背景颜色
        .cancel("取消分享")                      //设置底部按钮
        .setRow(3)                              //设置显示列数
        .itemClick(new OnItemClickListener() {  //设置监听
            @Override
            public void click(Item item) {
                Toast.makeText(MainActivity.this, getString(R.string.share_title) + item.getTitle(), Toast.LENGTH_LONG).show();
            }
        })
        .show();
```
## Listener 事件监听方式调用
    new BottomDialog(context)
        .title(R.string.share_title)
        .inflateMenu(R.menu.menu_share)
        .itemClick(new OnItemClickListener() {
            @Override
            public void click(Item item) {
                    //TODO 处理点击结果
                }
            })
        .show();
