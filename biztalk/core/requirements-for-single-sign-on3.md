---
title: "SSO 要求 TIBCO Rendevous 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d5c406b-f548-4df0-8644-fdf6a812a989
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40cf27a3b96534239fa871bd04b90febee9beafe
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="requirements-for-single-sign-on"></a>单一登录的要求

## <a name="prerequisites"></a>先决条件
若要使用单一登录 (SSO)，必须安装以下软件：  
  
-   Microsoft BizTalk Server
  
-   Visual Studio  
  
-   企业单一登录  
  
-   支持 SSO 某个服务器系统  
  
-   独立主机应配置为受信任验证。  
  
## <a name="enable-sso"></a>启用 SSO  
  
1.  在**传输属性**窗口中，选择**是**为**使用 SSO**。  
  
2.  在指定传输属性时选择相应的关联应用程序。  
  
 有关详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications1.md)。  
  
> [!NOTE]
>  后执行的操作使用 SSO，请记得重置到任何 Web 共享文件夹**不共享**。 使用该文件夹的应用程序将不更新，或如果共享文件夹，因为它被视为可在使用正常卸载。  
  
## <a name="see-also"></a>另请参阅  
[安全性](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)