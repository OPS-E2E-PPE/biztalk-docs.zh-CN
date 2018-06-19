---
title: 如何使用密码筛选器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb429f8b-c301-45a3-8a4f-bbe6f2c566a3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ad35e2c3bec5b2ece69911b8de8c7fd13c9b790
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255933"
---
# <a name="how-to-use-password-filters"></a>如何使用密码筛选器
ENTSSO 密码同步功能在 Microsoft Windows Active Directory 和非 Windows 系统之间同步密码。 但是，许多外部系统具有与 Active Directory 不同的密码策略要求。 （例如，IBM 系统可能要求密码为大写，并且仅限于 8 个字符。）这强制 ENTSSO 在两个系统之间使用“最小公分母”，从而限制了密码的安全性。  
  
 ENTSSO 密码筛选器功能解决此限制。 密码筛选器就是定义了额外属性的密码同步适配器。 这些额外属性（如最大或最小长度、大小写和字符限制）用于筛选密码，使其满足外部系统的条件。  
  
 请注意，创建密码筛选器时，指定的 Administrators 组将自动用作 SSO Administrators 帐户。 如果更改 SSO Administrators 组，则需要确保已使用新的 SSO Administrators 帐户更新密码筛选器。  
  
> [!NOTE]
>  与 ENTSSO 系统中的所有元素一样，密码筛选器包含高度敏感的信息，应向尽可能少的用户公开。  
  
### <a name="to-create-a-password-filter"></a>创建密码筛选器  
  
1.  在**SSO 管理控制台**，右键单击**密码管理**节点，，然后单击**创建筛选器**。  
  
     **密码筛选器向导**显示。  
  
2.  按照向导中的说明创建密码筛选器。  
  
### <a name="to-assign-an-affiliate-application-to-a-password-filter"></a>将关联应用程序分配到密码筛选器  
  
1.  右键单击相应的筛选器，并依次**分配**...  
  
2.  选择相应**Affiliate 应用程序**。