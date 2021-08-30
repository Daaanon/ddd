# ddd
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Тест задание</title>

    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-alpha.4/css/bootstrap.min.css" integrity="2hfp1SzUoho7/TsGGGDaFdsuuDL0LX2hnUp6VkX3CUQ2K4K+xjboZdsXyp4oUHZj" crossorigin="anonymous">
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-alpha.4/js/bootstrap.min.js" integrity="VjEeINv9OSwtWFLAtmc4JCtEJXXBub00gtSnszmspDLCtC0I4z4nqz7rEFbIZLLU" crossorigin="a"></script>
    </script>
<script>
        function getdetails(){
            var summ = $('#summ').val();
            var years = $('#years').val();
            $.ajax({
                type: "POST",
                url: "calc.php",
                data: {summ:summ, years:years}
            }).done(function( result )
            {
                $("#msg").html("Address of Roll no " +summ +" is "+result );
            });
        }
    </script>
</head>
<body>
<div class="logo"><img src="logo.png">
    </div>
            <div class="header__contacts">
              <a href="tel:+78001005005" class="header__tel-number-first">8-800-100-5005</a>
              <a href="tel:+73452522000" class="header__tel-number-second">+7(3452)522-000</a>

<div class="menu">
<ul>
    <li><a href="#">Кредитные карты</a></li>
    <li><a href="#">Вклады</a></li>
    <li><a href="#">Дебетовая карта</a></li>
    <li><a href="#">Страхование</a></li>
    <li><a href="#">Друзья</a></li>
    <li><a href="#">Интернет-банк</a></li>
</ul>
</div>
<section id = "inner-headline">
    <div class = "row">
        <div class = "col-lg-12">
            <?php if (!empty($crumbs)) { ?>
                <ul class="breadcrumb">
                    <?php foreach ($crumbs as $item) { ?>
                        <?php if (isset($item)) { ?>
                            <li>
                                <a href="<?php echo $item['url'] ?>"><?php echo $item['text'];if($item != end($crumbs)){echo '-></a>
                            </li>
                        <?php } ?>
                    <?php } ?>
                </ul>
            <?php } ?>
        </div>
    </div>
</section>
<div class="content">
    <div class="container">
        <h2>Калькулятор</h2>
    <form method="post" class="calc" >
        <div class="form-group row">
        <label for="date" class="col-sm-2 col-form-label">Дата оформления вклада</label>
            <div class="col-sm-10">
<!--                <input type="date"  name="date"><br>-->
                 <input type="text" id="datepicker" name="date">
            </div>
        </div>
        <div class="form-group row">
        <label for="summ" class="col-sm-2 col-form-label">Сумма</label>
            <div class="col-sm-10">
            <input type="number" name="summ" min="100" max="1000000"><br>
            </div>
        </div>
        <div class="form-group row">
            <label for="years" class="col-sm-2 col-form-label">Срок вклада</label>
        <div class="col-sm-10">
            <select name="years">
            <option value="365">1 год</option>
            <option value="730">2 года</option>
            <option value="1095">3 года</option>
            <option value="1460">4 года</option>
            <option value="1825">5 лет</option>
        </select>
        </div>
        </div>
        <div class="form-group row">
        <label for="replenishment" class="col-sm-2 col-form-label">Пополнение вклада</label>
           <div class="col-sm-10">
            <label><input type="radio" checked name="replenishment" value="false"/> Нет</label>
            <label><input type="radio"  name="replenishment" value="true"/> Да</label>
           </div>
           </div>
        <div class="form-group row">
            <label for="summadd" class="col-sm-2 col-form-label">Сумма пополнения вклада</label>
            <div class="col-sm-10">
            </div>
        </div>
            <input type="submit" class="btn btn-success" onClick = "getdetails()" value="Рассчитать">
        <div id="msg"></div>

    </form>
        </div>
</div>
    </main>
    <footer class="footer">
      <div class="container">
        <div class="footer__menu">
          <ul class="footer__list">
            <li class="footer__item"><a href="#"  <li><a href="#">Кредитные карты</a></li>
    <li><a href="#">Вклады</a></li>
    <li><a href="#">Дебетовая карта</a></li>
    <li><a href="#">Страхование</a></li>
    <li><a href="#">Друзья</a></li>
    <li><a href="#">Интернет-банк</a></li>
          </ul>
          </nav>
        </div>
        <div class="header__bottom">
          <nav class="header__breadcrumb">
            <ul class="header__breadcrumb-list">
              <li class="header__breadcrumb-item"><a 
    <li><a href="#">Главная</a></li>
    <li><a href="#">Вклады</a></li>
    <li><a href="#">Калькулятор</a></li>
            </ul>
          </nav>
        </div>
      </div>
      </div>
    </footer>
  </div>
</body>
</html>
