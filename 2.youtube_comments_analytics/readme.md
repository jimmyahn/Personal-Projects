

#개요
파이썬과 프로그래밍 방식 등 얕은 지식을 배웠지만 제대로 활용할 기회가 없었다. 
파이썬을 처음 배웠을 때 관심있었던 nlp을 활용할 수 있는 다른 프로젝트를 떠올렸다. 
기존에 즐겨보던 유튜브 크리에이터의 영상별, 성장별, 댓글과 좋아요 등 반응을 분석할 수 있을까. 호기심이 들었다. 
인플루언서의 충성고객의 심리는 여전히 남아있고 그 충성심이 인플루어서의 영향력을 만든다고 생각한다. 

#방법</br>
유튜브 api를 활용하고, 분석 툴은 파이썬을 활용.</br>
프로그래밍은 파이썬으로 진행한다.</br>

api에서 받아올 것 </br>
row: 영상 id</br>
columns</br>
-제목</br>
-댓글</br>
-업로드날짜</br>
-좋아요</br>
-싫어요</br>
-공유</br>
-구독</br>

데이터 적재 방법</br>
연습용 서버를 만들어서 데이터 베이스를 ?...</br>
mysql</br>

채널명 원지의 하루</br>
선정 이유 : 이 크리에이터는 지난 3년간의 기록을 남겨놨다.</br>
3년간의 시기에 비해 영상 업로드가 많지 않고 특징적인 3개의 시기로 분류 할 수 있다. </br>
1기. 아프리카 여행, 2기 미국 생활, 3기 여행유튜버 활동</br>
각 기수 마다 댓글의 반응에 특징이 있을 것이라는 가설을 세웠다.</br>


진행사항</br>
웹상에서 다른 사람이 올린 오픈소스를 활용하여 스켈레톤 구조를 맞춤.</br>
api 코드 입력 완료, 비디오id에 대해서 받아오기 가능.</br>
video_title, video_id, video_date 전부 받아왔음. nextPageToken 활용.</br>

해야할 것</br>
받아온 값들 테이블로 옮기기.</br>
statics 매서드 값도 정리하기.</br>


video table</br>
channel id</br>
video id</br>
title</br>
videodate</br>
viewcout</br>
likeCount</br>
dislikecount</br>
favorite count</br>
commnetcount</br>
duration</br>


comment table</br>
videoid</br>
commentDate</br>
commentId
comment</br>



video statics schema</br>

each video .comments, .statics schema</br>

한 것 :</br></br>
input channel id -> def get_video()( .playlist() ) -> output video id, video title</br>
input video id -> def get_comments() (.commentThreads()) -> output: each video’s comments, user name, comment date</br>
(unstructured data)</br>

해야할 것 : </br>
statics method </br>
(structured data)</br>
videos contentDetails.duration </br>
statistics.viewCount</br>
statistics.likeCount</br>
statistics.dislikeCount</br>
statistics.favoriteCount</br>
statistics.commentCount</br>

channelid</br>
videoid</br>
videotitle</br>
videodate</br>
videoduration</br>
view</br>
like</br>
dislike</br>
favorite</br>
commentcount</br>
authorname</br>
authorcomment</br>
commentdate</br>



매서드 request해서 받을 수 있는 최대량은 50개. nextpagetoken을 활용하면 5개단위로 페이지가 넘어감(5는 default) 다음 50개






