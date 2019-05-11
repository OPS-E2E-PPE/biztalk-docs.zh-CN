---
title: 如何删除 SSO |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, deleting
- SSO, deleting
- deleting, SSO
- deleting, Master Secret server
ms.assetid: 0e1ad8e3-0938-4f36-b85b-4631d0eeb8c9
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c72d8a0f718ce42adbae6eacde6b5a140d82469
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384260"
---
# <a name="how-to-remove-sso"></a>如何删除 SSO
如果你删除 BizTalk Server，除非依存产品要使用它不再配置企业单一登录 (SSO)。 但是，不将其删除。 必须单独删除 SSO。 您还可以还原包括主密钥以重复使用现有数据的配置信息。 有关详细信息，请参阅[如何还原主密钥](../core/how-to-restore-the-master-secret.md)。  
  
### <a name="to-remove-enterprise-single-sign-on"></a>若要删除企业单一登录  
  
1. 备份主密钥。 有关详细信息，请参阅[如何返回主密钥](../core/how-to-back-up-the-master-secret.md)。  
  
2. 卸载[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
3. 在 **“开始”** 菜单上，单击 **“控制面板”**。  
  
4. 单击**添加/删除程序**。  
  
5. 在中**添加/删除程序**对话框中，单击**Microsoft 企业单一登录**，然后单击**删除**。  
  
6. 单击**是**当系统提示你确认该删除的 Microsoft 企业单一登录。  
  
   > [!NOTE]
   >  如果你有 BizTalk Server 运行时、 开发或管理功能安装或安装 Host Integration Server 管理功能，您将不能卸载 SSO 运行时或管理组件，直到所有依赖项删除。  
  
## <a name="see-also"></a>请参阅  
 [安装 SSO](../core/installing-sso.md)