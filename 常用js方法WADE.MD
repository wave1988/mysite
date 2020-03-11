##### popupPage

```
popupPage("用户选择", "components.auth.UserListNew", "queryUserList", 
			  				"&cond_SERIAL_NUMBER=" +$("#AUTH_SERIAL_NUMBER").val(), null, "c_popup c_popup-half c_popup-half-hasBg", $.auth.afterSelectMoreUser, null);
```

##### MessageBox

```
MessageBox.alert('',"请先选择办理摄像头再新增 ！");
```

##### ajax

```
var param = "&SERIAL_NUMBER="+$("#AUTH_SERIAL_NUMBER").val();
	  			$.beginPageLoading("数据初始化。。。");
	  	$.ajax.submit(this, "getIpTvId", param, '', 
	  				function(dataset)
	  				{		
	  					if(dataset && dataset.length>0)
	  					{
	  						dataset.each
	  						(
  								function(info)
  								{
  									$("#NEXT_IPTV_ID").val(info.get("NEXT_IPTV_ID"));
  								}
	  						);
	  					}else{
	  						$("#NEXT_IPTV_ID").val("");
	  					} 
	  					   MagicBaseInfo.initMagicBaseInfo('3709',$("#AUTH_SERIAL_NUMBER").val(),"addMagicBtn",addrDesc);

  					$.endPageLoading();
  				}, 						 
  				function(error_code, error_info)
  				{
  					$.endPageLoading();
  					$.MessageBox.error(error_code, error_info);
  				}
  				,{"async":false}
  			);
```

