데이터 저장:  

 - Save 버튼을 더블클릭해서 onclick 이벤트를 생성.  
```
this.btn_save_onclick = function(obj:nexacro.Button,e:nexacro.ClickEventInfo)
{
    this.transaction(
	"strSave",					// 서비스 id
	"SvcURL::save_emp.jsp?arg=1&arg2=2",		// 서비스 url
	"in_emp=ds_emp:U",				// 저장 server ds = client ds
	"",						// 조회할 때 사용
	"arg1=1 arg2=" + nexacro.wrapQuote("2 3"),	// 문장의 끝 function(콜백함수)
	"fn_call");
};
```
 - 저장에서 :U를 설정하면 수정된 부분만 서버로 전송하고, :A를 설정하면 전체 데이터를 다 전송함. 모든 데이터를 다 넘겨야 하는 특별한 이유가 없는 이상 :U를 사용함.
