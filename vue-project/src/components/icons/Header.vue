<script type="text/javascript">
    $(function(){
        $('.menu-icon-show').click(function () {
            $('.login-nav ul').fadeToggle();
        });
                /*$('.menu-overlay').click(function(){
        $('.login-nav ul').fadeOut();

    $(this).fadeOut();
    return false;
                })*/

    $('.advanced-field').hide();
    $('.advance-search').click(function () {
        $('.advanced-field').slideToggle()
    });
            })

</script>

<style>
#in-header-middle-wrap {
       display: inline-block;
       min-height: 50px;
       width: 100%;
       margin-top: 10px;
       background: #222222;
   }

</style>

<template>
<header>
 
    <div class="menu-overlay"></div>
    
    <nav class="main-nav">
        <div class="container">
            <div class="row">
                <div class="col-md-2 col-lg-2">
                    <div class="menu-icon">
                        <a class="menu-icon-show"><i class="fa fa-bars"></i></a>
                        <a class="menu-icon-hide" style="display: none;"><i class="fa fa-times"></i></a>
                    </div>
                    <div class="site-logo">
                        <a href="indexc6e3.html?ref=logo">
                            <img class="big-logo" src="assets/img/logo.png" alt="logo" />
                            <img class="small-logo" src="assets/img/logo.png" alt="logo" />
                        </a>
                    </div>
                </div>
                <div class="col-md-8 col-lg-8">
                </div>
                <div class="col-md-2 col-lg-2">
                    <div class="right-nav">
                        <!-- <ul>
                            <li><a href="/" class="cart">Home</a></li>
                            <li><a href="/shop" class="cart">Buy Container</a></li>
                            <li><a href="/about" class="cart">About Us</a></li>
                            <li><a href="/career" class="cart">Career</a></li>
                            <li><a href="/contact" class="cart">Contact Us</a></li>
                            <li><a href=""><i class="fa fa-search"></i></a></li>
                            <li><a href="/shop/cart" class="cart"><i class="fa fa-shopping-cart text-white"></i><span class="text-white"> Cart (0)</span></a></li>
                        </ul> -->
                        <div class="login-nav" style="margin-right: 30px;">
                            <ul class="right-nav-li">
                                <!--<li>
                                        <a class="login-button" href="/userauth/login">
                                            <i class="fa fa-heart"></i> Favourite(0)
                                        </a>
                                    </li>-->
                                <li>
                                    <a class="login-button" href="userauth/login.html">
                                        <i class="fa fa-lock"></i> Login / signup
                                    </a>
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>

            <div class="clear"></div>
        </div>
    </nav>
</header>
</template>