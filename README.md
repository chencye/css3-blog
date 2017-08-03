# css3-blog

# 页头

```html
<header>
    <nav>
        <div class="logo"><a href="#">无钟声有</a></div>
        <ul>
            <li><a href="#" class="active">首页</a></li>
            <li><a href="#">链接2</a></li>
            <li><a href="#">链接3</a></li>
            <li id="sidebar_trigger"><a href="#">侧边栏菜单</a></li>
        </ul>
    </nav>
</header>
```

```css
header {
    background: rgba(0, 0, 0, 0.3);
}

nav {
    background: transparent;
    height: 50px;
}
nav ul {
    list-style: none;
    margin: 0;
    float: right;
}

nav ul li {
    display: inline-block;
    line-height: 50px;
}

nav ul li:last-child {
    margin-right: 30px;
}

nav ul li a {
    display: inline-block;
    padding: 0 10px;
    line-height: 50px;
    height: inherit;
    text-decoration: none;
    color: #fff;
}

nav .logo {
    display: inline-block;
    float: left;
    line-height: 50px;
    padding: 0 30px;
    font-size: 20px;
    font-weight: 700;
    letter-spacing: 1px;
}

nav .logo a {
    color: #fff;
    text-decoration: none;
}
```

## 卡片

```html
<div class="card-group clearfix">
    <div class="card">
        <h3>标题三</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
            tempor incididunt ut</p>
    </div>
    <div class="card">
        <h3>标题三</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
            tempor incididunt ut</p>
    </div>
    <div class="card">
        <h3>标题三</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
            tempor incididunt ut</p>
    </div>
    <div class="card">
        <h3>标题三</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
            tempor incididunt ut</p>
    </div>
</div>
```

```css
.clearfix:after {
    content: ' ';
    display: block;
    clear: both;
}

.card {
    float: left;
    width: 50%;
    min-height: 300px;
    padding: 50px;
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
}

.card p {
    font-size: 18px;
    letter-spacing: 1px;
}

.card:first-child {
    background: rgba(0, 0, 0, 0.04);
}

.card:nth-child(2) {
    background: rgba(0, 0, 0, 0.08);
}

.card:nth-child(3) {
    background: rgba(0, 0, 0, 0.12);
}

.card:nth-child(4) {
    background: rgba(0, 0, 0, 0.16);
}
```

## 侧边栏

```html
<div class="mask"></div>
<div id="sidebar">
    <ul>
        <li><a href="#">item1</a></li>
        <li><a href="#">item2</a></li>
        <li><a href="#">item3</a></li>
        <li><a href="#">item4</a></li>
        <li><a href="#">item5</a></li>
    </ul>
</div>
```

```css
.mask {
    display: none;
    position: fixed;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    background: rgba(0, 0, 0, 0.3);
}

#sidebar {
    position: fixed;
    top: 0;
    bottom: 0;
    right: -300px;
    width: 300px;
    background: #333;
    color: #fff;
    padding: 20px 0;
    transition: right 0.5s;
}

#sidebar ul {
    list-style-type: none;
    padding: 0;
    margin: 0;
}
#sidebar ul li a {
    display: inline-block;
    padding: 10px 30px;
    width: 100%;
    text-decoration: none;
    color: #fff;
}
#sidebar ul li a:hover {
    background-color: #444;
}
```

```javascript
    var sidebar = $("#sidebar"),
        mask = $(".mask"),
        sidebar_trigger = $("#sidebar_trigger");

    function showSideBar() {
        mask.fadeIn();
        sidebar.css({'right' : '0'});
    }
    function hideSideBar() {
        mask.fadeOut();
        sidebar.css({'right' : -sidebar.width()});
    }

    sidebar_trigger.on('click',showSideBar);
    mask.on('click',hideSideBar);
```

## 返回顶部

```html
<button class="back-to-top">返回顶部</button>
```

```css
button {
    border: none;
    background: #333;
    color: #eee;
    padding: 14px;
    border-radius: 8px;
}

.back-to-top {
    position: fixed; /** 以浏览器窗口为参照 **/
    bottom: 30px;
    right: 30px;
    border: 1px solid #888;
}
```

```javascript
    var sbackButton = $(".back-to-top");
    backButton.on('click', function() {
        $('html, body').animate({
            scrollTop: 0
        }, 500);
    });

    $(window).on('scroll', function() {
        if ($(window).scrollTop()> $(window).width()) {
            backButton.fadeIn();
        } else {
            backButton.fadeOut();
        }
    });

    $(window).trigger('scroll');
```
