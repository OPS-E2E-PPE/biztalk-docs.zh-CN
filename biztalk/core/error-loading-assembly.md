---
title: 加载程序集时出错 |Microsoft 文档
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
ms.openlocfilehash: 13be3acf6974565c86cc87b14ed58929553d5220
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241733"
---
# <a name="error-loading-assembly"></a>加载程序集时出错
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|此错误指示该位置不可以是完全受信任是否在网络共享上。 检查区域的代码访问安全策略。 或者，文件可能不是 BizTalk .NET 程序集。 检查的程序集 [程序集： BizTalkAssembly] 自定义属性。 或者，文件可能不是 .NET 程序集。 如果文件是 .dll 或 exe，则可能为非托管代码|  
  
## <a name="explanation"></a>解释  
 此错误指示该位置不可以是完全受信任是否在网络共享上。 检查区域的代码访问安全策略。 或者，文件可能不是 BizTalk .NET 程序集。 检查的程序集 [*程序集： BizTalkAssembly*] 自定义属性。 或者，文件可能不是 .NET 程序集。 如果文件是 .dll 或 exe，则可能为非托管代码。  
  
## <a name="user-action"></a>用户操作  
 如果位置的来源可靠，则为其授予完全信任级别。  确保 dll 是有效的 BizTalk .net 程序集。