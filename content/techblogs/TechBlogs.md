+++
title = 'Request Headers and Response Headers'
date = 2024-07-02T20:18:08+05:30
draft = true
tags= ['API']
author ='Aravind Yamana'
+++


## What are Request Headers? 

In simple terms additional meta-data sent by the client to server are called Request Headers , some of the main important request headers are as below 

## 1)User-Agent : 
	
	This header reveals the client identity such as browser name, browser version,OS version etc.

## 2)Connection : 
	This header reveals the  State of connectivity between client and server , possibe values are {keep-alive;close}

## 3)Accept     : 
	This header reveals the client prefernce format (eg .JSON,XML,HTML,XML,YAML etc) in which the server response to be sent to the client 

## 4)Accept-Lang: 
	This header reveals the client prefernce language (eg .EN-US,EN-IND,EN-GB etc) in which the server response to be sent to the client 

## 5)Content-Type:
	This header reveals the type of content/format (eg.json,xml,html,yaml) which client vis sending the request body/payload to the server

## 6)Authorization : 
	This header reveals the user auth details to the server to establish the client identity to the server

## Ok, Now lets understand What are Response Headers 

In simple terms additional meta-data sent by the server to client are called Response Headers , some of the main important request headers are as below 

## 1)User-Agent : 
	
	This header reveals the client identity such as browser name, browser version,OS version etc.

## 2)Connection : 
	This header reveals the  State of connectivity between client and server , possibe values are {keep-alive;close}

## 3)Accept     : 
	This header reveals the client prefernce format (eg .JSON,XML,HTML,XML,YAML etc) in which the server response to be sent to the client 

## 4)Accept-Lang: 
	This header reveals the client prefernce language (eg .EN-US,EN-IND,EN-GB etc) in which the server response to be sent to the client 

## 5)Content-Type:
	This header reveals the type of content/format (eg.json,xml,html,yaml) which client vis sending the request body/payload to the server

## 6)Authorization : 
	This header reveals the user auth details to the server to establish the client identity to the server