---
title: 如何禁用的用户映射 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disabling, maps
- managing [SSO maps], disabling
- maps [SSO], disabling
ms.assetid: 9b6eaff2-674b-49f7-8d5c-3e040a7dc7f8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b17ab68356d5d39f3f839f736261d4a7ef79c78
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "25968947"
---
# <a name="how-to-disable-a-user-mapping"></a>如何禁用的用户映射
当需要关闭与给定映射关联的所有操作时，可以禁用用户映射。 在删除用户映射之前必须禁用该映射。  
  
 当禁用用户映射时，它将显示为 (D) *\<域\>\\< 用户名\>* 时列出的用户映射。  
  
### <a name="to-disable-a-user-mapping-using-the-administration-utility"></a>使用管理实用工具禁用用户映射  
  
1.  上 **启动** 菜单上，单击 **运行**, ，然后键入 **cmd**。  
  
2.  在命令行上，转至企业单一登录安装目录。 默认安装目录是*\<驱动器\>*: \program Files\Enterprise 单一登录。  
  
3.  类型 **ssomanage-disablemapping *\<域\>*\\*\<用户名\>\<应用程序名称\>* * *，其中*\<域\>* 是用户帐户的 Windows 域和*\<用户名\>* 是 Windows 用户名称想要禁用凭据，为和*\<应用程序名称\>* 是你想要删除的用户映射的关联应用程序的名称。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
### <a name="to-disable-a-user-mapping-using-the-client-utility"></a>使用客户端实用工具禁用用户映射  
  
1.  上 **启动** 菜单上，单击 **运行**, ，然后键入 **cmd**。  
  
2.  在命令行上，转至企业单一登录安装目录。 默认安装目录是*\<驱动器\>*: \program Files\Enterprise 单一登录。  
  
3.  类型 * * ssoclient – disablemapping *\<应用程序名称\>* * *，其中*\<应用程序名称\>* 是你想要删除的用户映射的关联应用程序的名称。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>另请参阅  
 [SSO 映射](../core/sso-mappings.md)   
 [管理关联应用程序](../core/managing-affiliate-applications.md)   
 [管理用户映射](../core/managing-user-mappings.md)