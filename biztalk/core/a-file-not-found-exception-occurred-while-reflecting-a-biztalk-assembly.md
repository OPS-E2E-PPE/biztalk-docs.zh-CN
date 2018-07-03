---
title: 找不到文件专用于反映将 BizTalk 程序集时发生异常 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 223147eb-785f-4dfc-b2a6-7d50dfaf8092
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee0cffc331765924b4fe7d29d95f7094b14aecb3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000838"
---
# <a name="a-file-not-found-exception-occurred-while-reflecting-a-biztalk-assembly"></a>反射 BizTalk 程序集时发生异常，未找到某个文件
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                                                           |
| 产品版本 |                                                                                                                                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                                                                       |
|    事件 ID     |                                                                                                                                                                   0                                                                                                                                                                    |
|  事件源   |                                                                                                                                                                   0                                                                                                                                                                    |
|    组件    |                                                                                                                                                                   0                                                                                                                                                                    |
|  符号名称  |                                                                                                                                                                   0                                                                                                                                                                    |
|  消息正文   | 找不到文件专用于反映将 BizTalk 程序集时出现异常"{0}"。 如果一个或多个依存关系不可用，则可能发生此问题。 若要更正此问题，请尝试以下项之一： 1。 将程序集的依存关系复制到同一文件夹。 2. 将缺少的依存关系安装到全局程序集缓存中。 |

## <a name="explanation"></a>解释  
 此错误表明正在发布的 BizTalk 程序集引用了不在全局程序集缓存 (GAC) 或相同目录中的其他程序集。  

## <a name="user-action"></a>用户操作  
 除了错误消息中指定的操作之外，将引用程序集移到全局程序集缓存，或将其复制到与 BizTalk 程序集相同的位置。  

1. 单击**启动**，依次指向**所有程序**，指向**Visual Studio**，然后单击**Visual Studio**。  

2. 打开命令提示符。  

3. 浏览到该程序集的位置并输入**gacutil /I /\<**<em>程序集名称</em>**\>.dll**
