# Template commands Commands
```
	// avaible functions
	xml2str,dec2hex,hex2dec,hex2str,str2hex,htmlchars,escape,unescape,encodeURIComponent,decodeURIComponent
	{vars-htmlchars->name}
	{vars-html->name}

	// return javascript code ( additional reserver var framework )
	{{ document.getElementsByTagName('a').href.htmlchars() }}
	{{ (''+vars.obj.par).sha1() }}
	{js-return}
		return (''+tpl.text).sha1();
	{/js-return}

	{js-script}
		document.title = '123';
	{/js-script}
	
	// eval 
	// reserved vars: text, vars, tpl, i, replacers
	{eval} .. {/eval}

	{css-style}
		body {
			background: #fff;
		}
	{/css-style}

	{code}
		<h1> Here can be inserted HTML Code that will not be parsed
		and also code like <link /> .. <style />
	{/code}

	{vars->variable-name}		include a variable from view vars
	
	{params->dir->tpl}		return tpl dir
	{params->dir->js}		return JavaScript Controllers dir
	
	{params->dir->data}		return static data directory ...
	
	{use->css->location from static data}

	{use->less->location from static data}
	
	{use->js->location from static data}
	
	{use->css->css/styles.css}
	<div class="header">
		<a href="#!"><div class="logo">
		{include-tpl->workspace-header/logo}
		</div></a>
	
		<div class="header-box idex-box">
		{include-tpl->workspace-header/user-box}
		</div>
	
		<div class="header-login">
		{include-tpl->workspace-header/login}
		</div>
	</div>
	<img src="{params->dir->data}images/logo.png">

	{use->css->css/styles.css}

	<div class="header">
		<a href="#!"><div class="logo1">
		{vars->tpl---workspace-header__logo-header-register}
		</div></a>
	
		<div class="header-box">
		{include-tpl->workspace-header/user-box}
		</div>
	
		<div class="header-login">
		{include-tpl->workspace-header/login}
		</div>
	</div>

<script type="text/javascript">
	app.framework.view('#container_header','workspace-header');
	app.framework.view('#container_body','workspace-body/body');
	
	app.framework.$('#container div') // return array of divs
	
	app.framework.$('#container div[0]')	// return first div


	_ : function(c,a,p,d,app){
		// load page body-structure
		app.framework.view('#container_header','workspace-header',{
			var1	: 'value1',
			var2	: 'value2'
		});
		app.framework.view('#container_body','search/search');
		
		app.framework.exec( controller = 'index',action = '_',params = [],hide = false,skipHub = false, skipExec = false )
		
		app.framework.waitUntil(function(v,app){
			// do something ....
			app.$('#facebook-login-button').onclick	= function(){
				new m_urlload('php/api.php',function(url,text,vars,get,post,fullUrl){
					...
				},{
					controller	: c
				},{
					_m	: 'login',
					login	: ''
				},false);
				
				app.framework.exec(vars.controller,'action-name',[.. params ..],hide = true);
			}
		},function(v,app){
			// after this return true
			return app.$('#facebook-login-button')
		})
		
		
		app.framework.view(__app__.p.E(__app__.space).d()._(),'profile/login');
		app.framework.waitUntil(function(vars,app){
			__app__.p.I('profile-login-button').V({onclick: function(){
			 	m_login.exec('__app__.app.controller.actions.profile.login_addlinks');
			}});
			app.framework.waitUntil(function(vars,app){
				__app__.p.I('profile-login-preloading').F({ display : 'none'})
				.I('profile-login-button').F({ display : 'block' });
				// m_login.exec('__app__.app.controller.actions.profile.login_addlinks');
			},3000)
		},'#profile-login-preloading',{});
		
		
		app.framework.waitUntil(function(vars,app){
		
		},5000,{});
		
		
		app.framework.view(function(text,app,sett,tpl,vars) {
		
		},'profile/login',{ /* vars */ },{ /* sett */ });
		
		
		//app.framework.exec(c,'_update_',[],true);
	}
```