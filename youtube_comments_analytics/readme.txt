한 유튜브 채널에서 3가지 분류의 영상 댓글을 분석해본다.
유튜브 크리에이터 영상별 댓글 분석, 광고영상별 댓글분석, 성장시기별 댓글분석

개요
파이썬과 프로그래밍 방식 등 얕은 지식을 배웠지만 제대로 활용할 기회가 없었다. 
파이썬을 처음 배웠을 때 관심있었던 nlp을 활용할 수 있는 다른 프로젝트를 떠올렸다. 
기존에 즐겨보던 유튜브 크리에이터의 영상별, 성장별, 댓글과 좋아요 등 반응을 분석할 수 있을까. 호기심이 들었다. 
인플루언서의 충성고객의 심리는 여전히 남아있고 그 충성심이 인플루어서의 영향력을 만든다고 생각한다. 

방법
유튜브 api를 활용하고, 분석 툴은 파이썬을 활용.
프로그래밍은 파이썬으로 진행한다.
api에서 받아올 것
row: 영상 id
columns
-제목
-댓글
-업로드날짜
-좋아요
-싫어요
-공유
-구독

데이터 적재 방법
연습용 서버를 만들어서 데이터 베이스를 ?...
mysql

채널명 원지의 하루
선정 이유 : 이 크리에이터는 지난 3년간의 기록을 남겨놨다.
3년간의 시기에 비해 영상 업로드가 많지 않고 특징적인 3개의 시기로 분류 할 수 있다. 
1기. 아프리카 여행, 2기 미국 생활, 3기 여행유튜버 활동
각 기수 마다 댓글의 반응에 특징이 있을 것이라는 가설을 세웠다.


진행사항
웹상에서 다른 사람이 올린 오픈소스를 활용하여 스켈레톤 구조를 맞춤.
api 코드 입력 완료, 비디오id에 대해서 받아오기 가능.
video_title, video_id, video_date 전부 받아왔음. nextPageToken 활용.

해야할 것
받아온 값들 테이블로 옮기기.
statics 매서드 값도 정리하기.


video table
channel id
video id
title
videodate
viewcout
likeCount
dislikecount
favorite count
commnetcount
duration


comment table
videoid
commentDate
commentId
comment



video statics schema

each video .comments, .statics schema

한 것 :
input channel id -> def get_video()( .playlist() ) -> output video id, video title
input video id -> def get_comments() (.commentThreads()) -> output: each video’s comments, user name, comment date
(unstructured data)

해야할 것 : 
statics method 
(structured data)
videos contentDetails.duration 
statistics.viewCount
statistics.likeCount
statistics.dislikeCount
statistics.favoriteCount
statistics.commentCount

channelid
videoid
videotitle
videodate
videoduration
view
like
dislike
favorite
commentcount
authorname
authorcomment
commentdate



매서드 request해서 받을 수 있는 최대량은 50개. nextpagetoken을 활용하면 5개단위로 페이지가 넘어감(5는 default) 다음 50개






