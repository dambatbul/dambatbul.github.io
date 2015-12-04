---
layout: post
title: "GIT 사용가이드"
description: ""
category: 
tags: [tip]
---
{% include JB/setup %}

## merge two git repositories

	$ git clone git@gitorious/projA.git projA
	$ git clone git@gitorious/projB.git projB
	
	$ cd projB
	$ git remote add projA ../projA/
	$ git fetch projA
	$ git merge projA/master
	$ git push

---------------------------


## svn to git migration

git에 새로운 프로젝트를 만든 후 git repository를 받아오기

받아온 git 프로젝트로 이동 후 config 설정(Optional)

	$ git config --global user.name "xxx"
	$ git config --global user.email "xxx@gridwiz.com"
	
아래의 명령을 통해 svn repository 설정

	$ git svn init http://subversion/repo --no-metadata
	
svn 저장소의 소스 가져오기

	$ git svn fetch
	
git 저장소 업데이트 하기

	$ git push --set-upstream origin master

---------------------------


## 브랜치 tips

보기:

	$ git branch -a

	or
	
	$ git remote show origin


새로운 브렌치 생성:

	$ git checkout -b [name_of_your_new_branch]


새로운 브랜치 리포트 추가:

	$ git push origin [name_of_your_new_branch]

Add a new remote for your branch :

	$ git remote add [name_of_your_remote] 

Update your branch when the original branch from official repository has been updated :

	$ git fetch [name_of_your_remote]

Then you need to apply to merge changes, if your branch is derivated from develop you need to do :

	$ git merge [name_of_your_remote]/develop

브렌치 삭제:

	$ git branch -d [name_of_your_new_branch]

	or To force the deletion of local branch on your filesystem :

	$ git branch -D [name_of_your_new_branch]

원격 저장소 브렌치 삭제 :

	$ git push origin :[name_of_your_new_branch]

---------------------------
