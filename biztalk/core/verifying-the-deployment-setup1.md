---
title: "验证部署安装 1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CLASSPATH, verifying
- deployment, verifying setup
ms.assetid: 6c719e4c-9a61-480f-a4e4-0a1c518d1364
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5799d164dc2470236c3ab0286e38d19986a4d5a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="verifying-the-deployment-setup"></a>验证部署安装
在使用 BizTalk Server 导入绑定文件之前，必须验证以下各项：  
  
-   CLASSPATH 指向特定于 JD Edwards EnterpriseOne 文件的特定位置。 验证在新计算机上这些文件的位置是否相同，否则编辑绑定文件。  
  
-   用于响应的文件夹存在，并且在新计算机上相同，否则编辑绑定文件。  
  
-   如果在配置中存在 JD Edwards EnterpriseOne 系统密码，则在绑定文件中另存为 *****。 有关详细信息请参阅[部署限制](../core/deployment-limitations4.md)。  
  
## <a name="see-also"></a>另请参阅  
 [部署端口和程序集](../core/deploying-ports-and-assemblies3.md)