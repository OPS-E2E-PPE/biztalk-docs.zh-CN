---
title: 单一登录的要求 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1111377-2fe1-4d65-ac0d-c89d2f1740b8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f69bd8a232ba49f9e4ebb2eb3e53a70704bf0d80
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240395"
---
# <a name="requirements-for-single-sign-on"></a>单一登录的要求
若要使用单一登录 (SSO)，您必须安装以下软件：  
  
-   Microsoft BizTalk Server
  
-   Visual Studio  
  
-   企业单一登录  
  
-   支持 SSO 的服务器系统  
  
-   独立主机应配置为**受信任验证**。  
  
## <a name="enable-sso"></a>启用 SSO  
  
1. 在中**传输属性**窗口中，选择**是**有关**使用 SSO**。  
  
2. 指定传输属性时，请选择相应的关联应用程序。  
  
   有关创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications4.md)。  
  
> [!NOTE]
>  执行相应操作后使用 SSO，请重置到任何 Web 共享文件夹**不共享**。 使用该文件夹的应用程序将不更新，或如果共享的文件夹，因为它被视为在使用中正确卸载。  
  
## <a name="see-also"></a>请参阅  
 [用于 JD Edwards EnterpriseOne 的 BizTalk 适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)