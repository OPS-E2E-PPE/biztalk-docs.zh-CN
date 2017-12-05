---
title: "找不到文件反映 BizTalk 程序集时出现异常 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 223147eb-785f-4dfc-b2a6-7d50dfaf8092
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00000896eb4cb97e44ed51602675fc65495552be
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="a-file-not-found-exception-occurred-while-reflecting-a-biztalk-assembly"></a>反射 BizTalk 程序集时发生异常，未找到某个文件
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|反射 BizTalk 程序集“{0}”时发生找不到文件的异常。 如果一个或多个依存关系不可用，则可能发生此问题。 若要更正此问题，请尝试下列选项之一： 1。 将程序集的依存关系复制到同一文件夹。 2. 将缺少的依存关系安装到全局程序集缓存中。|  
  
## <a name="explanation"></a>解释  
 此错误表明正在发布的 BizTalk 程序集引用了不在全局程序集缓存 (GAC) 或相同目录中的其他程序集。  
  
## <a name="user-action"></a>用户操作  
 除了错误消息中指定的操作之外，将引用程序集移到全局程序集缓存，或将其复制到与 BizTalk 程序集相同的位置。  
  
1.  单击**启动**，指向**所有程序**，指向**Visual Studio**，然后单击**Visual Studio**。  
  
2.  打开命令提示符。  
  
3.  浏览到的程序集的位置并输入**gacutil /I /\<***程序集名称***\>.dll**