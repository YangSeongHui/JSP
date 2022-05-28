1. JDBC 순서 잊지말기.
(1) driver 연결
(2) 계정 연결
(3) query 준비
(4) query 실행 및 리턴
(5) db 종료

insert, update, delete는 갯수(int)가 리턴된다.

DTO : Data Transfer Object : 테이블의 row하나의 값이 dto에 들어간다.

myselect.jsp
<%
	int myno = Integer.parseInt(request.getParameter("myno"));  
    //쿼리스트링 : http요청의 파라미터 값을 얻기 위해 사용(request.getParameter()) -> string타입을 리턴한다.
	//request(내장객체)
    //myno를 가지고 글을 상세보기.
	MyDao dao = new MyDao();
	MyDto dto = dao.selectOne(myno);

%>

myupdate.jsp
<%
	int myno = Integer.parseInt(request.getParameter("myno"));
	MyDao dao = new MyDao();
	MyDto dto = dao.selectOne(myno);  //dto의 selectOne에서 myno로 찾은 값을 dto에 저장.
%>	

myinsert.jsp
form태그에서는 name값이 넘어가니, 꼭 써주자!

