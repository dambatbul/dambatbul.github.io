---
layout: post
title: "GIT 사용가이드"
description: ""
category: 
tags: [tip]
---
{% include JB/setup %}

## 병합하기
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


새로운 브렌치 생성:

	$ git checkout -b [name_of_your_new_branch]


새로운 브랜치 리포트 추가:

	$ git push origin [name_of_your_new_branch]

로컬 브랜치와 remote브랜치간 연동:

	$ git branch --set-upstream-to origin/[name_of_your_new_branch]

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

## commit 한 log 수정하기

Git은 자동으로 브랜치와 HEAD가 지난 몇 달 동안에 가리켰었던 커밋을 모두 기록하는데 이 로그를 Reflog라고 부른다.
로그 head 보기:

	$ git reflog

rebase -i 를 사용하여 수정할 커밋을 선택(최근 2개 기준).

	$ git rebase -i HEAD~2

	pick 9a54fd4 commit의 설명 추가
	pick 0d4a808 pull 설명을 추가

	# Rebase 326fc9f..0d4a808 onto d286baa
	#
	# Commands:
	#  p, pick = use commit
	#  r, reword = use commit, but edit the commit message
	#  e, edit = use commit, but stop for amending
	#  s, squash = use commit, but meld into previous commit
	#  f, fixup = like "squash", but discard this commit's log message
	#  x, exec = run command (the rest of the line) using shell
	#
	# If you remove a line here THAT COMMIT WILL BE LOST.
	# However, if you remove everything, the rebase will be aborted.
	#

수정할 줄의 pick 문자를 edit으로 변경하여 저장 · 종료. 
이후 파일 변경등을 한 후, commit --amend 를 실행하여 변경한 내용을 저장
이때 로그를 변경할 수 있음.

	$ git commit --amend

이 커밋 작업이 종료했다는 것을 알리려면, --continue 옵션을 지정하여 rebase 를 실행.

	$ git rebase --continue


이후 branch 정보를 확인하면, no branch 로 표시되어 있음.
master 브렌치로 merge해야함.

	$ git checkout master 
	$ git merge 9a54fd4

---------------------------

