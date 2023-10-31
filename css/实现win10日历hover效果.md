```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>win10日历效果</title>
    <style>
        table {
            width: 385px;
            height: 350px;
            background: #1a1a1a;
            color: #fff;
            text-align: center;
            font-size: 14px;
        }

        td,
        th {
            display: inline-block;
            width: 42px;
            height: 42px;
            margin: 3px;
            padding: 3px;
        }

        table span {
            display: block;
            background: #1a1a1a;
            line-height: 21px;
        }

        .disable {
            color: #5a5a5a;
        }

        .active {
            width: 48px;
            height: 48px;
            background: #3c3c3c;
            border: 1px solid #5faceb;
            box-sizing: border-box;
        }

        .active span {
            background: #0078d7;
            line-height: 20px;
        }

        .hover1 {
            background-image: radial-gradient(63px at 63px 63px, #3c3c3c, #1a1a1a);
        }

        .hover2 {
            background-image: radial-gradient(63px at 21px 63px, #3c3c3c, #1a1a1a);
        }

        .hover3 {
            background-image: radial-gradient(63px at -21px 63px, #3c3c3c, #1a1a1a);
        }

        .hover4 {
            background-image: radial-gradient(63px at 63px 21px, #3c3c3c, #1a1a1a);
        }

        .hover5 {
            background: #3c3c3c;
        }

        .hover6 {
            background-image: radial-gradient(63px at -21px 21px, #3c3c3c, #1a1a1a);
        }

        .hover7 {
            background-image: radial-gradient(63px at 63px -21px, #3c3c3c, #1a1a1a);
        }

        .hover8 {
            background-image: radial-gradient(63px at 21px -21px, #3c3c3c, #1a1a1a);
        }

        .hover9 {
            background-image: radial-gradient(63px at -21px -21px, #3c3c3c, #1a1a1a);
        }
    </style>
</head>

<body>
    <table>
        <tr>
            <th>一</th>
            <th>二</th>
            <th>三</th>
            <th>四</th>
            <th>五</th>
            <th>六</th>
            <th>七</th>
        </tr>
        <tr>
            <td class="disable"><span>29</span><span>廿一</span></td>
            <td class="disable"><span>30</span><span>廿二</span></td>
            <td class="disable"><span>31</span><span>廿三</span></td>
            <td><span>1</span><span>廿四</span></td>
            <td><span>2</span><span>廿五</span></td>
            <td><span>3</span><span>廿六</span></td>
            <td><span>4</span><span>廿七</span></td>
        </tr>
        <tr>
            <td><span>5</span><span>廿八</span></td>
            <td><span>6</span><span>廿九</span></td>
            <td><span>7</span><span>立冬</span></td>
            <td><span>8</span><span>十月</span></td>
            <td><span>9</span><span>初二</span></td>
            <td><span>10</span><span>初三</span></td>
            <td><span>11</span><span>初四</span></td>
        </tr>
        <tr>
            <td><span>12</span><span>初五</span></td>
            <td><span>13</span><span>初六</span></td>
            <td><span>14</span><span>初七</span></td>
            <td><span>15</span><span>初八</span></td>
            <td><span>16</span><span>初九</span></td>
            <td><span>17</span><span>初十</span></td>
            <td><span>18</span><span>十一</span></td>
        </tr>
        <tr>
            <td><span>19</span><span>十二</span></td>
            <td><span>20</span><span>十三</span></td>
            <td><span>21</span><span>十四</span></td>
            <td><span>22</span><span>小雪</span></td>
            <td><span>23</span><span>十六</span></td>
            <td><span>24</span><span>十七</span></td>
            <td><span>25</span><span>十八</span></td>
        </tr>
        <tr>
            <td><span>26</span><span>十九</span></td>
            <td><span>27</span><span>二十</span></td>
            <td><span>28</span><span>廿一</span></td>
            <td><span>29</span><span>廿二</span></td>
            <td><span>30</span><span>廿三</span></td>
            <td class="disable"><span>1</span><span>廿四</span></td>
            <td class="disable"><span>2</span><span>廿五</span></td>
        </tr>
    </table>
</body>

</html>
<script src="https://cdn.staticfile.org/jquery/1.10.2/jquery.min.js"></script>
<script>
    $('td').click(function () {
        $('td').removeClass('active');
        $(this).addClass('active')
    })
    // 切换块才会触发
    $('td').hover(function () {
        var i = $('td').index(this), length = $('td').length;
        $('td').removeClass('hover1 hover2 hover3 hover4 hover5 hover6 hover7 hover8 hover9')
        // 常规设置
        $(this).addClass('hover5')
        $('td').eq(i - 8).addClass('hover1')
        $('td').eq(i - 7).addClass('hover2')
        $('td').eq(i - 6).addClass('hover3')
        $('td').eq(i - 1).addClass('hover4')
        $('td').eq(i + 1).addClass('hover6')
        $('td').eq(i + 6).addClass('hover7')
        $('td').eq(i + 7).addClass('hover8')
        $('td').eq(i + 8).addClass('hover9')

        // 碰壁处理
        // left
        if (i % 7 == 0) {
            $('td').eq(i - 8).removeClass('hover1')
            $('td').eq(i - 1).removeClass('hover4')
            $('td').eq(i + 6).removeClass('hover7')
        }
        // top
        if (i < 7) {
            $('td').eq(i - 8).removeClass('hover1')
            $('td').eq(i - 7).removeClass('hover2')
            $('td').eq(i - 6).removeClass('hover3')
        }
        // right
        if ((i + 1) % 7 == 0) {
            $('td').eq(i - 6).removeClass('hover3')
            $('td').eq(i + 1).removeClass('hover6')
            $('td').eq(i + 8).removeClass('hover9')
        }
        // bottom
        if (i > 27) {
            $('td').eq(i + 6).removeClass('hover7')
            $('td').eq(i + 7).removeClass('hover8')
            $('td').eq(i + 8).removeClass('hover9')
        }
    })
    // 移动鼠标触发
    $('td').mousemove(function (e) {
        // 移除所有行内样式
        $("td").removeAttr("style");
        var even = e || event, mouseX, mouseY, eleX, eleY,numX, numY,originX,originY;
        // 当前鼠标坐标
        mouseX = e.clientX;
        mouseY = e.clientY;
        // 当前元素坐标
        eleX = $(this).offset().left;
        eleY = $(this).offset().top;
        // 高光圆的原点坐标
        originX = $('td').width()*3/2;
        originY = $('td').height()*3/2;
        // 差值
        numX = mouseX - eleX;
        numY = mouseY - eleY;
        // 计算倍数公式：原点/n+差值 = 样式表中固定的位置
        // 注：计算时差值取中间值，即差值的范围是0-42，取21
        $('.hover1').css('background-image',`radial-gradient(${originX}px at ${originX/1.5+numX}px ${originY/1.5+numY}px, #3c3c3c, #1a1a1a)`);
        $('.hover2').css('background-image',`radial-gradient(${originX}px at ${numX}px ${originY/1.5+numY}px, #3c3c3c, #1a1a1a)`);
        $('.hover3').css('background-image',`radial-gradient(${originX}px at ${originX/-1.5+numX}px ${originY/1.5+numY}px, #3c3c3c, #1a1a1a)`);
        $('.hover4').css('background-image',`radial-gradient(${originX}px at ${originX/1.5+numX}px ${numY}px, #3c3c3c, #1a1a1a)`);
        $('.hover6').css('background-image',`radial-gradient(${originX}px at ${originX/-1.5+numX}px ${numY}px, #3c3c3c, #1a1a1a)`);
        $('.hover7').css('background-image',`radial-gradient(${originX}px at ${originX/1.5+numX}px ${originY/-1.5+numY}px, #3c3c3c, #1a1a1a)`);
        $('.hover8').css('background-image',`radial-gradient(${originX}px at ${numX}px ${originY/-1.5+numY}px, #3c3c3c, #1a1a1a)`);
        $('.hover9').css('background-image',`radial-gradient(${originX}px at ${originX/-1.5+numX}px ${originY/-1.5+numY}px, #3c3c3c, #1a1a1a)`);
    })
</script>
```