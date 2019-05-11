---
title: 示例进行交互和 FileAct 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8552167c-2acc-4eae-a86a-55ba2e54d4a2
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 776659a7bcd6c882a514098758385123e4cfc0ea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366519"
---
# <a name="sample-interact-and-fileact-messages"></a><span data-ttu-id="cc502-102">示例进行交互和 FileAct 消息</span><span class="sxs-lookup"><span data-stu-id="cc502-102">Sample InterAct and FileAct Messages</span></span>
<span data-ttu-id="cc502-103">下面给出了 InterAct 和 FileAct 实时消息的示例。</span><span class="sxs-lookup"><span data-stu-id="cc502-103">Samples of InterAct and FileAct real-time messages are given below.</span></span>  
  
 <span data-ttu-id="cc502-104">**示例 InterAct 实时消息**</span><span class="sxs-lookup"><span data-stu-id="cc502-104">**Sample InterAct real-time message**</span></span>  
  
```  
<SwInt-ExchangeRequest>  
<SwInt-Request>  
<SwInt-RequestPayload>  
TestPayloadRequestSnF  
</SwInt-RequestPayload>  
</SwInt-Request>  
</SwInt-ExchangeRequest>  
```  
  
 <span data-ttu-id="cc502-105">**示例 FileAct 实时消息 （put 的请求）**</span><span class="sxs-lookup"><span data-stu-id="cc502-105">**Sample FileAct real-time message (put request)**</span></span>  
  
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
  
 <span data-ttu-id="cc502-106">**示例 FileAct 实时消息 （get 请求）**</span><span class="sxs-lookup"><span data-stu-id="cc502-106">**Sample FileAct real-time message (get request)**</span></span>  
  
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
  
