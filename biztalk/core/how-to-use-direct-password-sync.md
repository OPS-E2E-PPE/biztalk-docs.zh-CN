---
title: 如何使用直接密码同步 |Microsoft Docs
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
ms.openlocfilehash: e9baa74b383ee30c1fba70c7f9bb966706d60142
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333537"
---
# <a name="how-to-use-direct-password-sync"></a>如何使用直接密码同步
此版本的企业单一登录包括了从 Windows 功能直接进行密码同步。 这使你可以绕过密码同步适配器和更新 SSO 数据库中直接从 Windows 中的密码。  
  
 从 Windows 直接进行密码同步是在以下情况下有用：  
  
-   企业系统要求 Windows 到 Windows 的映射。  
  
-   您需要为 Windows 用户的密码更改时直接更新 SSO 数据库中的外部用户的密码。 可以通过使用其他机制更改密码的后端系统上 （相对应的外部用户）。 例如，可以使用 Microsoft Identity Integration Server 更新中资源的访问控制工具 (RACF) 使用 RACF Management Agent IBM 大型机上的密码。  
  
### <a name="to-enable-direct-password-sync"></a>若要启用直接密码同步  
  
1.  打开企业单一登录。  
  
2.  在作用域窗格中，单击**关联应用程序**。  
  
3.  右键单击相应**关联应用程序**。  
  
4.  单击 **“属性”**。  
  
     **关联的应用程序属性**对话框随即出现。  
  
5.  单击**选项**选项卡。  
  
6.  选择**从 Windows 直接进行密码同步**复选框。  
  
7.  单击“确定” 。