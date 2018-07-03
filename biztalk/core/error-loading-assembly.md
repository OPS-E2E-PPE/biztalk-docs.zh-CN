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
ms.openlocfilehash: df561b964faa0fae80f41f1423d3034466bbb8ce
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994950"
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
|  消息正文   | 此错误表示位置的网络共享上是否可能不完全受信任。 检查区域的代码访问安全策略。 或者，文件可能不是 BizTalk .NET 程序集。 检查的程序集 [程序集： BizTalkAssembly] 自定义属性。 或者，文件可能不是 .NET 程序集。 如果文件是 .dll 或 exe，则可能为非托管代码 |
  
## <a name="explanation"></a>解释  
 此错误表示位置的网络共享上是否可能不完全受信任。 检查区域的代码访问安全策略。 或者，文件可能不是 BizTalk .NET 程序集。 检查的程序集 [*程序集： BizTalkAssembly*] 自定义属性。 或者，文件可能不是 .NET 程序集。 如果文件是 .dll 或 exe，则可能为非托管代码。  
  
## <a name="user-action"></a>用户操作  
 如果位置的来源可靠，则为其授予完全信任级别。  确保 dll 是有效的 BizTalk .net 程序集。