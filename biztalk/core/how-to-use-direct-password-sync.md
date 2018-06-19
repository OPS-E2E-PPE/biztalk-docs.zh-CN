---
title: 如何使用直接密码同步 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1334c2f-2020-46ea-a98c-f7688813e38c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6080589271d845432e875cb335a2ef354c9784ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255941"
---
# <a name="how-to-use-direct-password-sync"></a>如何使用直接密码同步
此版本的企业单一登录包括了从 Windows 直接进行密码同步的功能。 这样，您便可以绕过密码同步适配器，直接从 Windows 更新 SSO 数据库中的密码。  
  
 从 Windows 直接进行密码同步这一功能在以下情况下十分有用：  
  
-   您的企业系统要求 Windows 到 Windows 的映射。  
  
-   在 Windows 用户的密码发生更改时，您需要对 SSO 数据库中的外部用户的密码进行更新。 可以使用其他机制更改外部用户所对应的后端系统中的密码。 例如，可以使用 Microsoft Identity Integration Server，通过 RACF Management Agent 更新 IBM 大型机上 Resource Access Control Facility (RACF) 中的密码。  
  
### <a name="to-enable-direct-password-sync"></a>启用直接密码同步  
  
1.  打开企业单一登录。  
  
2.  在作用域窗格中，单击**Affiliate 应用程序**。  
  
3.  右键单击相应**Affiliate 应用程序**。  
  
4.  单击 **“属性”**。  
  
     **Affiliate 应用程序属性**对话框随即出现。  
  
5.  单击**选项**选项卡。  
  
6.  选择**直接从 Windows 的密码同步**复选框。  
  
7.  单击 **“确定”**。