---
title: 如何使用密码筛选器 |Microsoft Docs
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
ms.openlocfilehash: 22b7939c7a6e00404c9c1b4db586cc9723504aa6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383357"
---
# <a name="how-to-use-password-filters"></a>如何使用密码筛选器
ENTSSO 密码同步功能同步 Microsoft Windows Active Directory 和非 Windows 系统之间的密码。 但是，许多外部系统具有不同于在 Active Directory 中密码策略要求。 (例如，IBM 系统可能要求密码为大写并且时间限制为 8 个字符。)这强制 ENTSSO 使用"最小公分"两个系统，限制密码安全性之间。  
  
 ENTSSO 密码筛选器功能来解决此限制。 密码筛选器是只是密码同步适配器定义的其他属性。 这些额外属性 （如最大或最小长度、 区分和字符限制） 用于筛选密码，以便它们满足外部系统的条件。  
  
 请注意，当您创建密码筛选器，指定的管理员组自动用作 SSO Administrators 帐户。 如果更改 SSO 管理员组，您需要确保密码筛选器也会更新为新的 SSO 管理员帐户。  
  
> [!NOTE]
>  与 ENTSSO 系统中的所有元素，如密码筛选器包含高度敏感的信息，并应被公开到人们可能的最小数目。  
  
### <a name="to-create-a-password-filter"></a>若要创建密码筛选器  
  
1.  在中**SSO 管理控制台**，右键单击**密码管理**节点，，然后单击**创建筛选器**。  
  
     **密码筛选器向导**出现。  
  
2.  按照向导创建密码筛选器的说明进行操作。  
  
### <a name="to-assign-an-affiliate-application-to-a-password-filter"></a>若要将分配到密码筛选器的关联应用程序  
  
1.  右键单击相应的筛选器，然后依次**分配**...  
  
2.  选择适当**关联应用程序**。