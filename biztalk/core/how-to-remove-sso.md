---
title: 如何删除 SSO |Microsoft 文档
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
ms.openlocfilehash: 7134186161c3c0647a20047afcbbe317fcbad1ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254653"
---
# <a name="how-to-remove-sso"></a>如何删除 SSO
除非依存产品要使用企业单一登录 (SSO)，否则在删除 BizTalk Server 时将不再配置 SSO。 不过，这样并未删除 SSO。 您必须单独删除 SSO。 也可以还原包括主密钥在内的配置信息以重用现有数据。 有关详细信息，请参阅[如何还原主密钥](../core/how-to-restore-the-master-secret.md)。  
  
### <a name="to-remove-enterprise-single-sign-on"></a>删除企业单一登录  
  
1.  备份主密钥。 有关详细信息，请参阅[如何返回向上主密钥](../core/how-to-back-up-the-master-secret.md)。  
  
2.  卸载 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
3.  在 **“开始”** 菜单上，单击 **“控制面板”**。  
  
4.  单击**添加/删除程序**。  
  
5.  在**添加/删除程序**对话框中，单击**Microsoft Enterprise 上单一登录**，然后单击**删除**。  
  
6.  单击**是**当系统提示确认该删除的 Microsoft Enterprise 上单一登录。  
  
    > [!NOTE]
    >  如果已安装 BizTalk Server 运行时、开发或管理功能，或已安装 Host Integration Server 管理功能，则只有在删除所有依赖项后，才能卸载该 SSO 运行时或管理组件。  
  
## <a name="see-also"></a>另请参阅  
 [安装 SSO](../core/installing-sso.md)