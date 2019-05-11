---
title: 加载程序集时出错 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 600973e0-3142-455f-9afa-74430af31e38
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 665b6b00aca8f7f059f021bfc2e1c5803bfc0156
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388768"
---
# <a name="error-loading-assembly"></a>加载程序集时出错
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                                                                                                      |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                                                                          |
| 产品版本 |                                                                                                                                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                                                                                      |
|    事件 ID     |                                                                                                                                                                                  0                                                                                                                                                                                   |
|  事件源   |                                                                                                                                                                                  0                                                                                                                                                                                   |
|    组件    |                                                                                                                                                                                  0                                                                                                                                                                                   |
|  符号名称  |                                                                                                                                                                                  0                                                                                                                                                                                   |
|  消息正文   | 此错误表示位置的网络共享上是否可能不完全受信任。 检查该区域的代码访问安全策略。 或者，文件可能不是 BizTalk.NET 程序集。 检查的程序集 [程序集：BizTalkAssembly] 自定义属性。 或者，文件可能不是.NET 程序集。 如果文件是.dll 或 exe，则可能为非托管的代码 |
  
## <a name="explanation"></a>解释  
 此错误表示位置的网络共享上是否可能不完全受信任。 检查该区域的代码访问安全策略。 或者，文件可能不是 BizTalk.NET 程序集。 检查的程序集 [*程序集：BizTalkAssembly*] 自定义属性。 或者，文件可能不是.NET 程序集。 如果文件是.dll 或 exe，则可能为非托管的代码。  
  
## <a name="user-action"></a>用户操作  
 如果它来自可靠来源位置授予完全信任级别。  请确保 dll 是有效的 BizTalk.net 程序集。