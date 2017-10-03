---
title: "示例交互和 FileAct 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8552167c-2acc-4eae-a86a-55ba2e54d4a2
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30c2541e2ec3a6fe77de374843a47befacf3a791
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sample-interact-and-fileact-messages"></a><span data-ttu-id="c2224-102">示例交互和 FileAct 消息</span><span class="sxs-lookup"><span data-stu-id="c2224-102">Sample InterAct and FileAct Messages</span></span>
<span data-ttu-id="c2224-103">下面提供的交互和 FileAct 实时消息的示例。</span><span class="sxs-lookup"><span data-stu-id="c2224-103">Samples of InterAct and FileAct real-time messages are given below.</span></span>  
  
 <span data-ttu-id="c2224-104">**示例交互实时消息**</span><span class="sxs-lookup"><span data-stu-id="c2224-104">**Sample InterAct real-time message**</span></span>  
  
```  
<SwInt-ExchangeRequest>  
<SwInt-Request>  
<SwInt-RequestPayload>  
TestPayloadRequestSnF  
</SwInt-RequestPayload>  
</SwInt-Request>  
</SwInt-ExchangeRequest>  
```  
  
 <span data-ttu-id="c2224-105">**示例 FileAct 实时消息 （put 请求）**</span><span class="sxs-lookup"><span data-stu-id="c2224-105">**Sample FileAct real-time message (put request)**</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Sw-ExchangeFileRequest>  
<Sw-FileRequest>  
<Sw-FileOpRequest>  
<Sw-PutFileRequest>  
<Sw-PhysicalName>%PhysicalFolderName%\sample_put.txt</Sw-PhysicalName>  
</Sw-PutFileRequest>  
</Sw-FileOpRequest>  
</Sw-FileRequest>  
</Sw-ExchangeFileRequest>  
```  
  
 <span data-ttu-id="c2224-106">**示例 FileAct 实时消息 （get 请求）**</span><span class="sxs-lookup"><span data-stu-id="c2224-106">**Sample FileAct real-time message (get request)**</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Sw-ExchangeFileRequest>  
<Sw-FileRequest>  
<Sw-FileOpRequest>  
<Sw-GetFileRequest>  
<Sw-PhysicalName>%PhysicalFolderName%\sample_get.txt</Sw-PhysicalName>  
</Sw-GetFileRequest>  
</Sw-FileOpRequest>  
</Sw-FileRequest>  
</Sw-ExchangeFileRequest>  
```  
  
