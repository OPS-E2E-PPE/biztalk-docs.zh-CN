---
title: TIBCO Rendevous 适配器的 SSO 要求 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d5c406b-f548-4df0-8644-fdf6a812a989
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08fc69294b5f2ca7a773adf64175b210604091c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396153"
---
# <a name="requirements-for-single-sign-on"></a>单一登录的要求

## <a name="prerequisites"></a>先决条件
若要使用单一登录 (SSO)，您必须：  
  
-   Microsoft BizTalk Server
  
-   Visual Studio  
  
-   企业单一登录  
  
-   支持 SSO 的服务器系统  
  
-   独立主机应配置为受信任的身份验证。  
  
## <a name="enable-sso"></a>启用 SSO  
  
1. 在中**传输属性**窗口中，选择**是**有关**使用 SSO**。  
  
2. 指定传输属性时，请选择相应的关联应用程序。  
  
   有关详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications1.md)。  
  
> [!NOTE]
>  执行相应操作后使用 SSO，请重置到任何 Web 共享文件夹**不共享**。 使用该文件夹的应用程序将不更新，或如果共享的文件夹，因为它被视为在使用中正确卸载。  
  
## <a name="see-also"></a>请参阅  
[安全性](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)