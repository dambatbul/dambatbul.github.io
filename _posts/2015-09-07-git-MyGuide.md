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


## 원격 브랜치가져오기

	$ git checkout -b env origin/dev-env-refactoring
	Branch env set up to track remote branch dev-env-refactoring from origin.
	Switched to a new branch ‘env’
	$ git branch
	* env
	master
	$ git branch -a
	* env
	master
	remotes/origin/HEAD -> origin/master
	remotes/origin/dev-env-refactoring
	remotes/origin/gh-pages
	remotes/origin/master
	
---------------------------
