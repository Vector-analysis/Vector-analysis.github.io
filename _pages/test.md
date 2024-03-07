---
title: "Test"
layout: homepageDefault
permalink: /test/
---

<!DOCTYPE html>
<html lang="zh-cn">
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta name="referrer" content="origin-when-cross-origin" />
    <meta name="description" content="双摆杆运动模型。初始条件的微小差异，会导致千差万别的运动现象，这是混沌理论重要体现。主要考虑初始条件有两摆杆长度、质量、初始摆杆角度、重力加速度。 input: % 参数定义 L1 = 1; % 第一根摆长 L2 = 0.5; % 第二根摆长 m1 = 1; % 第一根摆质量 m2 = 0.5; %" />
    <meta property="og:description" content="双摆杆运动模型。初始条件的微小差异，会导致千差万别的运动现象，这是混沌理论重要体现。主要考虑初始条件有两摆杆长度、质量、初始摆杆角度、重力加速度。 input: % 参数定义 L1 = 1; % 第一根摆长 L2 = 0.5; % 第二根摆长 m1 = 1; % 第一根摆质量 m2 = 0.5; %" />
    <meta http-equiv="Cache-Control" content="no-transform" />
    <meta http-equiv="Cache-Control" content="no-siteapp" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <title>【matlab混沌理论】1.4.双摆杆的不同参数模型 - 屋檐下的树叶 - 博客园</title>
        <link rel="canonical" href="https://www.cnblogs.com/liaowangta/p/17898236.html" />
    <link id="favicon" rel="shortcut icon" href="//common.cnblogs.com/favicon.svg" type="image/svg+xml" />
    
    <link rel="stylesheet" href="/css/blog-common.min.css?v=-ZyqVZFpbeqegERiw6IFl5UCgzkddUyNI63o0PKVWZc" />
    

    
        <link id="highlighter-theme-cnblogs" type="text/css" rel="stylesheet" href="/css/hljs/cnblogs.css?v=5J1NDtbnnIr2Rc2SdhEMlMxD4l9Eydj88B31E7_NhS4" />
    <link type="text/css" rel="stylesheet" href="https://www.cnblogs.com/liaowangta/custom.css?v=4XOzTNDRnFnAVS&#x2B;q60pWDQBsP5A=" />
    <link type="text/css" rel="stylesheet" href="/css/fonts/JetBrainsMono-Regular.min.css" />
    <link id="mobile-style" media="only screen and (max-width: 767px)" type="text/css" rel="stylesheet" href="/skins/SimpleMemory/bundle-simplememory-mobile-pure.min.css?v=F2e9dMGzAUzDRZU-W-4qVsoLMeDjGqD2cUFxFY5EcWc" />
    
    <link type="application/rss+xml" rel="alternate" href="https://www.cnblogs.com/liaowangta/rss" />
    <link type="application/rsd+xml" rel="EditURI" href="https://www.cnblogs.com/liaowangta/rsd.xml" />
    <link type="application/wlwmanifest+xml" rel="wlwmanifest" href="https://www.cnblogs.com/liaowangta/wlwmanifest.xml" />
    <script>
        var currentBlogId = 593570;
        var currentBlogApp = 'liaowangta';
        var isLogined = false;
        var isBlogOwner = false;
        var skinName = 'SimpleMemory';
        var visitorUserId = '';
        var hasCustomScript = true;
        window.cb_enable_mathjax = true;
        window.mathEngine = 0;
        window.codeHighlightEngine = 1;
        window.enableCodeLineNumber = false;
        window.codeHighlightTheme = 'cnblogs';
        window.darkModeCodeHighlightTheme = 'vs2015';
        window.isDarkCodeHighlightTheme = false;
        window.isDarkModeCodeHighlightThemeDark = true;
        window.isDisableCodeHighlighter = false;
        window.enableCodeThemeTypeFollowSystem = false;
        window.enableMacStyleCodeBlock = false;
    </script>
        <script>
            window.currentPostId = 17898236;
            window.currentPostDateAdded = '2023-12-13 07:52';
        </script>
    <script src="https://common.cnblogs.com/scripts/jquery-3.3.1.min.js"></script>
    <script src="https://www-cdn.cnblogs.com/js/blog-common.min.js?v=hCFn3w0kqJuQLulgK4J8iHeB1qNZMGm8mIEL2Xhwe4g"></script>
        <script>updateCustomBlogReferrer();</script>
    
</head>
<body class="skin-simplememory no-navbar mathjax2">
    <a name="top"></a>
    <div id="top_nav" class="navbar forpc navbar-custom">
        <nav id="nav_main" class="navbar-main">
            <ul id="nav_left" class="navbar-list navbar-left">
                <li class="navbar-branding">
                    <a href="https://www.cnblogs.com/" title="开发者的网上家园" role="banner">
                        <img src="//common.cnblogs.com/logo.svg" alt="博客园Logo" />
                    </a>
                </li>
                <li><a href="https://cnblogs.vip/">会员</a></li>
                <li><a href="https://www.cnblogs.com/cmt/p/17974346">周边</a></li>
                <li>
                    <a href="https://news.cnblogs.com/" onclick="countClicks('nav', 'skin-navbar-news')">新闻</a>
                </li>
                <li>
                    <a href="https://q.cnblogs.com/" onclick="countClicks('nav', 'skin-navbar-q')">博问</a>
                </li>
                <li>
                    <a href="https://ai.hanghang.com/page/4649915" target="_blank">AI培训</a>
                </li>
                <li><a href="https://market.cnblogs.com" target="_blank">云市场</a></li>
            </ul>
            <ul id="nav_right" class="navbar-list navbar-right">
                <li>
                    <form id="zzk_search" class="navbar-search dropdown" action="https://zzk.cnblogs.com/s" method="get" role="search">
                        <input name="w" id="zzk_search_input" placeholder="代码改变世界" type="search" tabindex="3" autocomplete="off" />
                        <button id="zzk_search_button" onclick="window.navbarSearchManager.triggerActiveOption()">
                            <img id="search_icon" class="focus-hidden" src="//common.cnblogs.com/icons/search.svg" alt="搜索" />
                            <img class="hidden focus-visible" src="//common.cnblogs.com/icons/enter.svg" alt="搜索" />
                        </button>
                        <ul id="navbar_search_options" class="dropdown-menu quick-search-menu">
                            <li tabindex="0" class="active" onclick="zzkSearch(event, document.getElementById('zzk_search_input').value)">
                                <div class="keyword-wrapper">
                                    <img src="//common.cnblogs.com/icons/search.svg" alt="搜索" />
                                    <div class="keyword"></div>
                                </div>
                                <span class="search-area">所有博客</span>
                            </li>
                                    <li tabindex="1" onclick="zzkBlogSearch(event, 'liaowangta', document.getElementById('zzk_search_input').value)">
                                        <div class="keyword-wrapper">
                                            <img src="//common.cnblogs.com/icons/search.svg" alt="搜索" />
                                            <div class="keyword"></div>
                                        </div>
                                        <span class="search-area">当前博客</span>
                                    </li>
                        </ul>
                    </form>
                </li>
                <li id="navbar_login_status" class="navbar-list">
                    <a class="navbar-user-info navbar-blog" href="https://i.cnblogs.com/EditPosts.aspx?opt=1" alt="写随笔" title="写随笔">
                        <img id="new_post_icon" class="navbar-icon" src="//common.cnblogs.com/icons/newpost.svg" alt="写随笔" />
                    </a>
                    <a id="navblog-myblog-icon" class="navbar-user-info navbar-blog" href="https://passport.cnblogs.com/GetBlogApplyStatus.aspx" alt="我的博客" title="我的博客">
                        <img id="myblog_icon" class="navbar-icon" src="//common.cnblogs.com/icons/myblog.svg" alt="我的博客" />
                    </a>
                    <a class="navbar-user-info navbar-message navbar-icon-wrapper" href="https://msg.cnblogs.com/" alt="短消息" title="短消息">
                        <img id="msg_icon" class="navbar-icon" src="//common.cnblogs.com/icons/message.svg" alt="短消息" />
                        <span id="msg_count" style="display: none"></span>
                    </a>
                    <a id="navbar_lite_mode_indicator" data-current-page="blog" style="display: none" href="javascript:void(0)" alt="简洁模式" title="简洁模式启用，您在访问他人博客时会使用简洁款皮肤展示">
                        <img class="navbar-icon" src="//common.cnblogs.com/icons/lite-mode-on.svg" alt="简洁模式" />
                    </a>
                    <div id="user_info" class="navbar-user-info dropdown">
                        <a class="dropdown-button" href="https://home.cnblogs.com/">
                            <img id="user_icon" class="navbar-avatar" src="//common.cnblogs.com/icons/avatar-default.svg" alt="用户头像" />
                        </a>
                        <div class="dropdown-menu">
                            <a id="navblog-myblog-text" href="https://passport.cnblogs.com/GetBlogApplyStatus.aspx">我的博客</a>
                            <a href="https://home.cnblogs.com/">我的园子</a>
                            <a href="https://account.cnblogs.com/settings/account">账号设置</a>
                            <a href="javascript:void(0)" id="navbar_lite_mode_toggle" title="简洁模式会使用简洁款皮肤显示所有博客">
    简洁模式 <img id="navbar_lite_mode_on" src="/images/lite-mode-check.svg" class="hide" /><span id="navbar_lite_mode_spinner" class="hide">...</span>
</a>
                            <a href="javascript:void(0)" onclick="account.logout();">退出登录</a>
                        </div>
                    </div>
                    <a class="navbar-anonymous" href="https://account.cnblogs.com/signup">注册</a>
                    <a class="navbar-anonymous" href="javascript:void(0);" onclick="account.login()">登录</a>
                </li>
            </ul>
        </nav>
    </div>

    <div id="page_begin_html">
          <div id="set_btn_box">
    <div class="set_btn fly_top fadeIn animated">
        <svg class="icon" aria-hidden="true"><use xlink:href="#icon-zhiding"></use></svg>
    </div>
    <div class="set_btn article_icon_btn catalogue_btn">
        <svg class="icon" aria-hidden="true" style="color:#97A1A7"><use xlink:href="#icon-dagang"></use></svg>
    </div>
    <div class="set_btn article_icon_btn comment">
        <a href="#comment_form_container"><svg class="icon" aria-hidden="true" style="color:#97A1A7"><use xlink:href="#icon-linedesign-01"></use></svg></a>
    </div>
    <div class="set_btn skin_btn">
        <svg class="icon" aria-hidden="true" style="color:#97A1A7"><use xlink:href="#icon-pifu"></use></svg>
    </div>
    <div class="set_btn gratuity">
        <svg class="icon" aria-hidden="true" style="color:#97A1A7"><use xlink:href="#icon-dashang"></use></svg>
    </div>
    <div class="set_btn article_icon_btn artice_recommend">
        <svg class="icon" aria-hidden="true" style="color:#97A1A7"><use xlink:href="#icon-tuijian2"></use></svg>
    </div>
     <div id="thumsCanvas" width="200" height="400" style="width:100px;height:200px"></div>
    <div class="set_btn catalogue">
        <svg class="icon" aria-hidden="true" style="color:#97A1A7"><use xlink:href="#icon-cebianlan-"></use></svg>
    </div>
</div>
<script src='https://files.cnblogs.com/files/blogs/593570/canvas2.js'></script>
<!--
<link href="//files.cnblogs.com/files/linianhui/lnh.cnblogs.css" rel="stylesheet"/>-->

    </div>

    <!--done-->
<div id="home">
<div id="header">
	<div id="blogTitle">
        <a id="lnkBlogLogo" href="https://www.cnblogs.com/liaowangta/"><img id="blogLogo" src="/skins/custom/images/logo.gif" alt="返回主页" /></a>		
		
<!--done-->
<h1><a id="Header1_HeaderTitle" class="headermaintitle HeaderMainTitle" href="https://www.cnblogs.com/liaowangta">Leaves of Eaves</a>
</h1>
<h2>Leaves under the eaves. I found flowers on the branches of a tree, leaves falling soundly under the tree, and the roots of the tree are intricate and fractal. 译：我在某房子旁发现了：树上枝见有花，树下叶落有声，树根错综分形。</h2>




		
	</div><!--end: blogTitle 博客的标题和副标题 -->
	<div id="navigator">
		
<ul id="navList">
<li><a id="blog_nav_sitehome" class="menu" href="https://www.cnblogs.com/">
博客园</a>
</li>
<li>
<a id="blog_nav_myhome" class="menu" href="https://www.cnblogs.com/liaowangta/">
首页</a>
</li>
<li>

<a id="blog_nav_newpost" class="menu" href="https://i.cnblogs.com/EditPosts.aspx?opt=1">
新随笔</a>
</li>
<li>
<a id="blog_nav_contact" class="menu" href="https://msg.cnblogs.com/send/%E5%B1%8B%E6%AA%90%E4%B8%8B%E7%9A%84%E6%A0%91%E5%8F%B6">
联系</a></li>
<li>
<a id="blog_nav_rss" class="menu" href="javascript:void(0)" data-rss="https://www.cnblogs.com/liaowangta/rss/">
订阅</a>
<!--<partial name="./Shared/_XmlLink.cshtml" model="Model" /></li>--></li>
<li>
<a id="blog_nav_admin" class="menu" href="https://i.cnblogs.com/">
管理</a>
</li>
</ul>


		<div class="blogStats">
			<div id="blog_stats_place_holder"><script>loadBlogStats();</script></div>
		</div><!--end: blogStats -->
	</div><!--end: navigator 博客导航栏 -->
</div><!--end: header 头部 -->
<div id="main">
	<div id="mainContent">
	<div class="forFlow">
		<div id="post_detail">
    <!--done-->
    <div id="topics">
        <div class="post">
            <h1 class = "postTitle">
                
<a id="cb_post_title_url" class="postTitle2 vertical-middle" href="https://www.cnblogs.com/liaowangta/p/17898236.html">
    <span role="heading" aria-level="2">【matlab混沌理论】1.4.双摆杆的不同参数模型</span>
    

</a>

            </h1>
            <div class="clear"></div>
            <div class="postBody">
                <div id="cnblogs_post_body" class="blogpost-body blogpost-body-html">
<p><strong>双摆杆运动模型。</strong>初始条件的微小差异，会导致千差万别的运动现象，这是<a class="hl hl-1" href="https://so.csdn.net/so/search?q=%E6%B7%B7%E6%B2%8C&amp;spm=1001.2101.3001.7020" target="_blank" data-report-click="{&quot;spm&quot;:&quot;1001.2101.3001.7020&quot;,&quot;dest&quot;:&quot;https://so.csdn.net/so/search?q=%E6%B7%B7%E6%B2%8C&amp;spm=1001.2101.3001.7020&quot;,&quot;extra&quot;:&quot;{\&quot;searchword\&quot;:\&quot;混沌\&quot;}&quot;}" data-tit="混沌" data-pretit="混沌" rel="noopener">混沌</a>理论重要体现。主要考虑初始条件有两摆杆长度、质量、初始摆杆角度、重力加速度。</p>
<p>input:</p>
<div class="cnblogs_Highlighter">
<pre class="brush:matlab;gutter:true;">% 参数定义
L1 = 1;     % 第一根摆长
L2 = 0.5;   % 第二根摆长
m1 = 1;     % 第一根摆质量
m2 = 0.5;   % 第二根摆质量
g = 9.81;   % 重力加速度
 
% 初始状态定义
theta1 = pi/6;  % 第一根摆角度
theta2 = 0;     % 第二根摆角度
dtheta1 = 0;    % 第一根摆角速度
dtheta2 = 0;    % 第二根摆角速度
 
% 动画绘制
tspan = [0 30]; % 时间跨度
y0 = [theta1 dtheta1 theta2 dtheta2]; % 初始状态向量
[t, y] = ode45(@(t,y) pendulum2(t, y, L1, L2, m1, m2, g), tspan, y0); % 解微分方程
 
x1 = L1*sin(y(:,1)); % 第一根摆x坐标
y1 = -L1*cos(y(:,1)); % 第一根摆y坐标
x2 = L1*sin(y(:,1)) + L2*sin(y(:,3)); % 第二根摆x坐标
y2 = -L1*cos(y(:,1)) - L2*cos(y(:,3)); % 第二根摆y坐标
 
set(gcf, 'renderer', 'painters');
axis equal; % x、y轴比例相等
axis([-1.5*(L1+L2) 1.5*(L1+L2) -1.5*(L1+L2) 1.5]); % 设置坐标轴范围
hold on;
 
x1_trace = zeros(length(t), 1); % 第一个摆的摆顶端x坐标
y1_trace = zeros(length(t), 1); % 第一个摆的摆顶端y坐标
x2_trace = zeros(length(t), 1); % 第二个摆的摆顶端x坐标
y2_trace = zeros(length(t), 1); % 第二个摆的摆顶端y坐标
 
% 绘制双摆动画，同时画出摆顶端轨迹连线
for k = 1:length(t)-1
    plot([0 x1(k) x2(k)], [0 y1(k) y2(k)], 'linewidth', 0.5); % 绘制双摆图形
    plot(x2(1:k), y2(1:k), '.', 'color', [0.8 0.05 0.1], 'markersize', 10); % 绘制尾迹
    x1_trace(k+1) = L1*sin(y(k+1,1));
    y1_trace(k+1) = -L1*cos(y(k+1,1));
    x2_trace(k+1) = x1_trace(k+1) + L2*sin(y(k+1,3));
    y2_trace(k+1) = y1_trace(k+1) - L2*cos(y(k+1,3));
    plot([x1_trace(k) x1_trace(k+1)], [y1_trace(k) y1_trace(k+1)], 'linewidth', 1, 'color', 'blue'); % 第一个摆的轨迹线
    plot([x2_trace(k) x2_trace(k+1)], [y2_trace(k) y2_trace(k+1)], 'linewidth', 1, 'color', 'green'); % 第二个摆的轨迹线
    drawnow; % 实时显示
end
 
% 微分方程定义
function dydt = pendulum2(t, y, L1, L2, m1, m2, g)
    dydt = zeros(4,1);
 
    % 向量拆分为各个分量
    theta1 = y(1);
    dtheta1 = y(2);
    theta2 = y(3);
    dtheta2 = y(4);
 
    % 运动方程
    % 第一个摆的力
    F1 = -m1*L1*dtheta1^2*sin(theta1) - m1*g*cos(theta1)*sin(theta1);
    % 第二个摆的力
    F2 = -m2*(L1*dtheta1^2*sin(theta1) + L2*dtheta2^2*sin(theta2)) - m2*g*cos(theta2)*sin(theta2);
    % 坐标加速度
    d2theta1 = (F1 + m1*g*sin(theta1)*cos(theta1) + F2*cos(theta1-theta2))/(m1*L1^2 + m2*L1^2 - m2*L1*L2*cos(theta1-theta2));
    d2theta2 = (F2*cos(theta1-theta2) + (m1+m2)*g*sin(theta1) + L1*dtheta1^2*sin(theta1)*cos(theta1-theta2) - (m1+m2)*L2*dtheta2^2*sin(theta1-theta2))/(L2^2*m2 + (m1+m2)*L1^2 - 2*L1*L2*m2*cos(theta1-theta2));
 
    dydt(1) = dtheta1; % 第一个摆角速度
    dydt(2) = d2theta1; % 第一个摆角加速度
    dydt(3) = dtheta2; % 第二个摆角速度
    dydt(4) = d2theta2; % 第二个摆角加速度
end
</pre>
</div>
<p>output:</p>
<p>初始条件：L1 =&nbsp;1;L2 = 0.5;m1 = 1;m2 = 0.5;theta1 = pi/6;theta2 = 0;dtheta1 = 0;dtheta2 = 0;</p>
<p><img src="https://img2023.cnblogs.com/blog/1936803/202312/1936803-20231213074907548-1667611410.png" alt="" width="406" height="304" style="display: block; margin-left: auto; margin-right: auto"></p>
<p>&nbsp;output:</p>
<p>初始条件：第二摆杆长度是第一摆杆的一半，其余变量也不同。</p>
<p><img src="https://img2023.cnblogs.com/blog/1936803/202312/1936803-20231213075034319-1816022293.png" alt="" width="383" height="287" style="display: block; margin-left: auto; margin-right: auto"></p>
<p>output:</p>
<p>初始条件：第一摆杆长度、质量等于第一摆杆的，初始摆角不同。</p>
<p><img src="https://img2023.cnblogs.com/blog/1936803/202312/1936803-20231213075123667-604704775.png" alt="" width="409" height="307" style="display: block; margin-left: auto; margin-right: auto"></p>
</div>
<div id="MySignature" role="contentinfo">
    <p>本文来自博客园，作者：<a href="https://www.cnblogs.com/liaowangta/" target="_blank">屋檐下的树叶</a>，转载请注明原文链接：<a href="https://www.cnblogs.com/liaowangta/p/17898236.html" target="_blank">https://www.cnblogs.com/liaowangta/p/17898236.html</a></p>
</div>
<div class="clear"></div>
<div id="blog_post_info_block" role="contentinfo">
    <div id="blog_post_info"></div>
    <div class="clear"></div>
    <div id="post_next_prev"></div>
</div>
            </div>
            <div class="postDesc">posted @ 
<span id="post-date" data-last-update-days="85.42446229507523" data-date-created="BlogServer.Application.Dto.BlogPost.BlogPostDto" data-date-updated="2023-12-13 08:13">2023-12-13 07:52</span>&nbsp;
<a href="https://www.cnblogs.com/liaowangta">屋檐下的树叶</a>&nbsp;
阅读(<span id="post_view_count">34</span>)&nbsp;
评论(<span id="post_comment_count">0</span>)&nbsp;
<a href="https://i.cnblogs.com/EditPosts.aspx?postid=17898236" rel="nofollow">编辑</a>&nbsp;
<a href="javascript:void(0)" onclick="AddToWz(17898236);return false;">收藏</a>&nbsp;
<a href="javascript:void(0)" onclick="reportManager.report({ currentUserId: '', targetType: 'blogPost', targetId: '17898236', targetLink: 'https://www.cnblogs.com/liaowangta/p/17898236.html', title: '【matlab混沌理论】1.4.双摆杆的不同参数模型' })">举报</a>
</div>
        </div>
	    
	    
    </div><!--end: topics 文章、评论容器-->
</div>
<script>
    var cb_entryId = 17898236, cb_entryCreatedDate = '2023-12-13 07:52', cb_postType = 1, cb_postTitle = '【matlab混沌理论】1.4.双摆杆的不同参数模型';
    var allowComments = true, cb_blogId = 593570, cb_blogApp = 'liaowangta', cb_blogUserGuid = '3eb2f776-997c-48cc-bb07-08d7aab2198a';
    mermaidRender.render()
    markdown_highlight()
    zoomManager.apply("#cnblogs_post_body img:not(.code_img_closed):not(.code_img_opened)");    
</script>
<a id="!comments"></a>
<div id="blog-comments-placeholder"></div>
<div id="comment_form" class="commentform">
    <a name="commentform"></a>
    <div id="divCommentShow"></div>
    <div id="comment_nav">
            <a class="comment-nav-left forpc" href="https://cnblogs.vip/" target="_blank">会员力量，点亮园子希望</a>
        <div class="comment-nav-right">
            <span id="span_refresh_tips"></span><a href="#" onclick="return RefreshPage();">刷新页面</a><a href="#top">返回顶部</a>
        </div>
    </div>
    <div id="comment_form_container"></div>
    <div class="ad_text_commentbox" id="ad_text_under_commentbox"></div>
        <div id="cnblogs_ch"></div>
    <div id="opt_under_post"></div>
        <div id="cnblogs_c1" class="under-post-card">
            <a href="https://click.aliyun.com/m/1000390858/" rel="nofollow" target="_blank" onclick="countCreativeClicks('C1-阿里云-年度大降价')">
                <img src="https://img2024.cnblogs.com/blog/35695/202403/35695-20240305190919759-683110071.jpg" onload="countCreativeImpressions('C1-阿里云-年度大降价')" alt="" />
                <span id="c1_impression" style="display:none"></span>
            </a>
        </div>
    <div id="under_post_card1"></div>
    <div id="under_post_card2"></div>
    <div id="HistoryToday" class="under-post-card"></div>
    <script type="text/javascript">
        var commentManager = new blogCommentManager();
        commentManager.renderComments(0);
        fixPostBody();
        window.footnoteTipManager.generateFootnoteTips();

            window.tocManager.displayDisableTocTips = false;
            window.tocManager.generateToc();
            
                setTimeout(function() { countViews(cb_blogId, cb_entryId); }, 50);
            
            deliverT2();
            deliverC1C2();
            loadNewsAndKb();
            
                LoadPostCategoriesTags(cb_blogId, cb_entryId);
            
            LoadPostInfoBlock(cb_blogId, cb_entryId, cb_blogApp, cb_blogUserGuid);
            GetPrevNextPost(cb_entryId, cb_blogId, cb_entryCreatedDate, cb_postType);
            loadOptUnderPost();
            GetHistoryToday(cb_blogId, cb_blogApp, cb_entryCreatedDate);
                </script>
</div>

	</div><!--end: forFlow -->
	</div><!--end: mainContent 主体内容容器-->
	<div id="sideBar">
		<div id="sideBarMain">
			<div id="sidebar_news" class="newsItem">
    <h3 class="catListTitle">公告</h3>
<div id="blog-news">    
    <div id="sidebar_news_content">
    </div>
</div>
<script>loadBlogNews();</script>

 
</div>
<div id="sidebar_c3"></div>
			<div id="blog-calendar" style="display:none"></div><script>loadBlogDefaultCalendar();</script>			
			<div id="leftcontentcontainer">
				<div id="blog-sidecolumn"></div>
                    <script>loadBlogSideColumn();</script>
			</div>			
		</div><!--end: sideBarMain -->
	</div><!--end: sideBar 侧边栏容器 -->
	<div class="clear"></div>
	</div><!--end: main -->
	<div class="clear"></div>
	<div id="footer">
		<!--done-->
Copyright &copy; 2024 屋檐下的树叶
<br /><span id="poweredby">Powered by .NET 8.0 on Kubernetes</span>



	</div><!--end: footer -->
</div><!--end: home 自定义的最大容器 -->



    <div id="page_end_html">
        <style id="ceshicss">
@media (max-width: 767px){
#set_btn_box {width: 100vw;left: 0;right: 0;bottom: 0;background: hsla(0,0%,100%,1.0);height: 49px;display: flex;justify-content: space-between;align-items: center;padding: 12px 40px;border-top: 1px solid #e8e8e8;box-sizing: border-box;}
.set_btn {margin-top: 0;}
.set_btn.fly_top.fadeIn.animated {position: absolute;right: 10px;bottom: 60px;}
.container{bottom:50px}}
#mainContent{width:90%}
</style>

<link href="https://blog-static.cnblogs.com/files/blogs/593570/tippy.min.css" rel="stylesheet">
<script src="https://blog-static.cnblogs.com/files/blogs/593570/tippy.js"></script>
<link rel='stylesheet' href='https://cdn.bootcss.com/animate.css/3.7.2/animate.min.css'>
<script src="https://blog-static.cnblogs.com/files/blogs/593570/font_1825850_klax1ao4o6.css"></script>
<script src="https://blog-static.cnblogs.com/files/blogs/593570/three.min.js"></script>
<link rel="stylesheet" href="https://blog-static.cnblogs.com/files/blogs/593570/OwO.min.css" />
<script src="https://blog-static.cnblogs.com/files/blogs/593570/OwO2.min.js"></script>
<script src="https://blog-static.cnblogs.com/files/blogs/593570/monitoring2.js"></script>

<script>
miluframe({
  Youself:'https://www.cnblogs.com/liaowangta/', /*个人的博客园链接*/
  /*博客园导航信息*/
    custom:[{
      name:'首页',
      link:'https://www.cnblogs.com/liaowangta/',
      istarget:true
    },{
      name:'联系',
      link:'https://msg.cnblogs.com/send/%E9%BA%8B%E9%B9%BF%E9%B2%81%E5%93%9F',
      istarget:false
    },{
      name:'技能树',
      link:'https://github.com/Leavesueaves',
      istarget:true
    },{
      name:'文章',
      link:'https://www.cnblogs.com/liaowangta/my-articles',
      istarget:true
    },{
      name:'相册',
      link:'https://www.cnblogs.com/miluluyo/gallery.html',
      istarget:true
    },{
      name:'友链',
      link:'https://www.cnblogs.com/liaowangta/p/11633791.html',
      istarget:false
    },{
      name:'维护',
      link:'https://www.cnblogs.com/liaowangta/p/12092009.html',
      istarget:false
    },{
      name:'投喂',
      link:'https://www.cnblogs.com/miluluyo/p/gratuity.html',
      istarget:false
    },{
      name:'管理',
      link:'https://i.cnblogs.com/',
      istarget:true
    }],
    /*向别人展示自己的友链信息*/
    resume:{
        "name":"Leaves of Eaves",
        "link":"https://www.cnblogs.com/liaowangta/",
        "headurl":"https://images.cnblogs.com/cnblogs_com/blogs/593570/galleries/2276382/t_230225053637_20200206125355.png",
        "introduction":"我在某房子旁发现了：树上枝见有花，树下叶落有声，树根错综分形"
    },
    /*友链信息*/
    unionbox:[{
        "name":"Leaves of Eaves",
        "introduction":"没有标准答案,但有真理。",
        "url":"https://www.cnblogs.com/liaowangta/",
        "headurl":"https://images.cnblogs.com/cnblogs_com/blogs/593570/galleries/2276382/t_230225053637_20200206125355.png"
      },{
        "name":"Leaves of Eaves的技能树",
        "introduction":"我在某房子旁发现了：树上枝见有花，树下叶落有声，树根错综分形",
        "url":"https://github.com/Leavesueaves",
        "headurl":"https://images.cnblogs.com/cnblogs_com/blogs/593570/galleries/2276382/t_230225053637_20200206125355.png"
      }],
    /*友链表格头信息，这个可以忽略*/
    details:[{
        field: 'name',
        literal: '昵称',
      },{
        field: 'introduction',
        literal: '标语',
      },{
        field: 'url',
        literal: '链接地址',
      },{
        field: 'headurl',
        literal: '头像地址',
      }],
    /*浏览器顶部小图标*/
    logoimg:'https://images.cnblogs.com/cnblogs_com/blogs/593570/galleries/2276382/t_230225024803_hi.jpg',
    /*文章页面标题前的图标，此处图标有扩展，下面会提到图标*/
    cuteicon:['icon-caomei','icon-boluo','icon-huolongguo','icon-chengzi','icon-hamigua','icon-lizhi','icon-mangguo','icon-liulian','icon-lizi','icon-lanmei','icon-longyan','icon-shanzhu','icon-pingguo','icon-mihoutao','icon-niuyouguo','icon-xigua','icon-putao','icon-xiangjiao','icon-ningmeng','icon-yingtao','icon-taozi','icon-shiliu','icon-ximei','icon-shizi'],
    /*赞赏，若true则显示此按钮，false则不显示*/
    isGratuity:false,
    /*赞赏按钮焦点显示赞赏内容，内容可自行更改*/
    gratuity:'<div class="popper_box"><p><b>要请我喝奶茶吗  (づ｡◕ᴗᴗ◕｡)づ</b> </p><div class="popper_box_con"><div class="popper_box_con_li"><img src="https://images.cnblogs.com/cnblogs_com/blogs/593570/galleries/2276382/t_230225024803_hi.jpg" alt="">（^-^）</div><div class="popper_box_con_li"><img src="https://images.cnblogs.com/cnblogs_com/blogs/593570/galleries/2276382/t_230225024803_hi.jpg" >（^?^）</div></div><p><b>留下一句你觉得很励志与美的话给我吧~</b>&nbsp;&nbsp;<b><a rel="nofollow noopener"  href="https://www.cnblogs.com/miluluyo/p/12930946.html">GO</a></b></div>'
  })
})
</script>

<!-- 点赞 -->
<div width="1777" height="841" style="position: fixed; left: 0px; top: 0px; z-index: 2147483647; pointer-events: none;"></div><script src="https://blog-static.cnblogs.com/files/miluluyo/mouse-click.js"></script>

<!-- 以下内容是否添加你随意 -->

<script>

<!--2023动态蓝色网状线条，改造自开源js动画-->
/*关键参数：context.fillRect(r.x - 0.5, r.y - 0.5, 0.8, 0.8)，点的大小*/
/*关键参数：max: 26000，吸引子圈阈值半径的大小*/
<script type="text/javascript">
 
    !function () {
        //封装方法，压缩之后减少文件大小
        function get_attribute(node, attr, default_value) {
            return node.getAttribute(attr) || default_value;
        }
 
        //封装方法，压缩之后减少文件大小
        function get_by_tagname(name) {
            return document.getElementsByTagName(name);
        }
 
        //获取配置参数
        function get_config_option() {
            var scripts = get_by_tagname("script"),
                script_len = scripts.length,
                script = scripts[script_len - 1]; //当前加载的script
            return {
                l: script_len, //长度，用于生成id用
                z: get_attribute(script, "zIndex", -1), //z-index
                o: get_attribute(script, "opacity", 0.8), //opacity
                c: get_attribute(script, "color", "255,255,255"), //color
                n: get_attribute(script, "count", 188) //count
            };
        }
 
        //设置canvas的高宽
        function set_canvas_size() {
            canvas_width = the_canvas.width = window.innerWidth || document.documentElement.clientWidth || document.body.clientWidth,
                canvas_height = the_canvas.height = window.innerHeight || document.documentElement.clientHeight || document.body.clientHeight;
        }
 
        //绘制过程
        function draw_canvas() {
            context.clearRect(0, 0, canvas_width, canvas_height);
            //随机的线条和当前位置联合数组
            var e, i, d, x_dist, y_dist, dist; //临时节点
            //遍历处理每一个点
            random_points.forEach(function (r, idx) {
                r.x += r.xa,
                    r.y += r.ya, //移动
                    r.xa *= r.x > canvas_width || r.x < 0 ? -1 : 1,
                    r.ya *= r.y > canvas_height || r.y < 0 ? -1 : 1, //碰到边界，反向反弹
                    context.fillRect(r.x - 0.5, r.y - 0.5, 0.8, 0.8); //绘制一个宽高为1的点
                //从下一个点开始
                for (i = idx + 1; i < all_array.length; i++) {
                    e = all_array[i];
                    // 当前点存在
                    if (null !== e.x && null !== e.y) {
                        x_dist = r.x - e.x; //x轴距离 l
                        y_dist = r.y - e.y; //y轴距离 n
                        dist = x_dist * x_dist + y_dist * y_dist; //总距离, m
 
                        dist < e.max && (e === current_point && dist >= e.max / 2 && (r.x -= 0.02 * x_dist, r.y -= 0.02 * y_dist), //靠近的时候加速
                            d = (e.max - dist) / e.max,
                            context.beginPath(),
                            context.lineWidth = d / 2,
                            context.strokeStyle = "#00b0e6",
                            context.moveTo(r.x, r.y),
                            context.lineTo(e.x, e.y),
                            context.stroke());
                    }
                }
            }), frame_func(draw_canvas);
        }
 
        //创建画布，并添加到body中
        var the_canvas = document.createElement("canvas"), //画布
            config = get_config_option(), //配置
            canvas_id = "c_n" + config.l, //canvas id
            context = the_canvas.getContext("2d-disabled"), canvas_width, canvas_height,
            frame_func = window.requestAnimationFrame || window.webkitRequestAnimationFrame || window.mozRequestAnimationFrame || window.oRequestAnimationFrame || window.msRequestAnimationFrame || function (func) {
                window.setTimeout(func, 1000 / 40);
            }, random = Math.random,
            current_point = {
                x: null, //当前鼠标x
                y: null, //当前鼠标y
                max: 26000 // 圈半径的平方
            },
            all_array;
        the_canvas.id = canvas_id;
        the_canvas.style.cssText = "position:fixed;top:0;left:0;z-index:" + config.z + ";opacity:" + config.o;
        get_by_tagname("body")[0].appendChild(the_canvas);
 
        //初始化画布大小
        set_canvas_size();
        window.onresize = set_canvas_size;
        //当时鼠标位置存储，离开的时候，释放当前位置信息
        window.onmousemove = function (e) {
            e = e || window.event;
            current_point.x = e.clientX;
            current_point.y = e.clientY;
        }, window.onmouseout = function () {
            current_point.x = null;
            current_point.y = null;
        };
        //随机生成config.n条线位置信息
        for (var random_points = [], i = 0; config.n > i; i++) {
            var x = random() * canvas_width, //随机位置
                y = random() * canvas_height,
                xa = 2 * random() - 1, //随机运动方向
                ya = 2 * random() - 1;
            // 随机点
            random_points.push({
                x: x,
                y: y,
                xa: xa,
                ya: ya,
                max: 6500 //沾附距离
            });
        }
        all_array = random_points.concat([current_point]);
        //0.1秒后绘制
        setTimeout(function () {
            draw_canvas();
        }, 80);
    }();
</script>


<!-- 小鱼跃出水面的动画 -->
<div id="jsi-flying-fish-container" class="container" style="background-color:#fff"></div>
<script src='https://blog-static.cnblogs.com/files/blogs/593570/myfish.js'></script>
<style>
  @media only screen and (max-width: 767px){
  #sidebar_search_box input[type=text]{width:calc(100% - 24px);   }}
  #jsi-flying-fish-container{
    opacity: 0.4;
    position:fixed;
    width: 100%;
    height: 19%;
	bottom: 0;
  }
</style>
<!-- 小鱼 end -->

<!-- 鼠标特效烟花 -->
 <script src="https://blog-static.cnblogs.com/files/yjlblog/cursor-effects.js"></script>
 <div width="1366" height="662" style="position: fixed; left: 0px; top: 0px; z-index: 2147483647; pointer-events: none;"></div>
<style>
@media only screen and (max-width: 850px){
#sidebar_search_box input[type=text]{width:calc(100% - 24px)}
}
</style>

<!--点击冒点-->
<div width="1280" height="765" style="position: fixed; left: 0px; top: 0px; z-index: 2147483647; pointer-events: none;"></div>
<script src="https://blog-static.cnblogs.com/files/blogs/593570/mouse-click.js?t=1677290843"></script>
    </div>

    <input type="hidden" id="antiforgery_token" value="CfDJ8C838EyK0EpKpQQcC9VwxBn-_NKRJ6j1YsXyjbT6fTw9XxXazxGCmWvn_hTT_4QZVar0jjqCrsbas0X942vcDWA1lNj3sPIP2yozd1TLw9YEqR9Hx8dYq52VJs4eizAqyQoayMT9LRC6uua3GEBCOFI" />
    <script async src="https://www.googletagmanager.com/gtag/js?id=G-M95P3TTWJZ"></script>
<script>
    window.dataLayer = window.dataLayer || [];
    function gtag() { dataLayer.push(arguments); }
    gtag('js', new Date());
    gtag('config', 'G-M95P3TTWJZ');
</script>
<script defer src="https://hm.baidu.com/hm.js?866c9be12d4a814454792b1fd0fed295"></script>
</body>
</html>
