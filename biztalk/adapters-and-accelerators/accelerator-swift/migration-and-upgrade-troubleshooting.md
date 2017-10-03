---
title: "迁移和升级故障排除 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- upgrading, troubleshooting
- troubleshooting, upgrading
- troubleshooting, migrating
- migrating, troubleshooting
ms.assetid: 6e6c0ff9-7897-4de6-9e9b-b502b3a1785b
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c063e2e4ba213c3f72cbfb4977a3463d16b0a726
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="migration-and-upgrade-troubleshooting"></a>迁移和升级故障排除
## <a name="assemblies-need-to-be-undeployed-before-an-upgrade"></a>程序集需要升级之前未部署  
  
### <a name="symptom"></a>故障现象  
 当你尝试升级 A4SWIFT 时，则升级过程失败。  
  
### <a name="possible-cause"></a>可能的原因  
 在升级完成时，仍将部署以下 A4SWIFT 程序集： Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration、 Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas，Microsoft.Solutions.FinancialServices.SWIFT.MrsrService。  
  
> [!NOTE]
>  无需重新部署 Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas。 安装程序将重新部署该程序集。  
  
### <a name="solution"></a>解决方案  
 手动取消部署按以下顺序的四个 A4SWIFT 程序集：  
  
-   Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration  
  
-   Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas  
  
-   Microsoft.Solutions.FinancialServices.SWIFT.MrsrService。  
  
 在升级之后，重新部署这些程序集 (使用**BTSTask.exe**) 按相反的顺序。  
  
## <a name="an-upgrade-removes-access-permissions-for-the-service-folder"></a>升级会删除服务文件夹的访问权限  
  
### <a name="symptom"></a>故障现象  
 升级到之后[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]，%programfiles%\Microsoft BizTalk Accelerator for SWIFT\Service 文件夹的访问权限不正确。  
  
### <a name="possible-cause"></a>可能的原因  
 当你升级到[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]，升级过程从 %programfiles%\Microsoft BizTalk Accelerator for SWIFT\Service 文件夹中移除 A4SWIFT 管理员和 A4SWIFT 用户组的访问权限。  
  
### <a name="solution"></a>解决方案  
 如果你遇到此问题，手动设置的服务文件夹的以下访问权限：  
  
|组或用户名|权限|  
|------------------------|----------------|  
|A4SWIFT 管理员|完全控制|  
|A4SWIFT 用户|读取及执行|  
  
 若要设置这些权限，请继续执行，如下所示：  
  
 在[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器中，移动到*%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\Service。  
  
1.  右键单击服务文件夹，单击**属性**，然后单击**安全**选项卡。  
  
2.  在组或用户名称窗格中的服务属性对话框中，单击**添加**，输入 ***\<服务器名称 >*\A4SWIFT 管理员**，然后单击**确定**。  
  
    > [!NOTE]
    >  如果 A4SWIFT Administrators 组的域组，请输入 ***\<域名 >*\A4SWIFT 管理员**。  
  
3.  重复步骤 2  ***\<服务器名称 >*\A4SWIFT 用户**，或  **\<*域名*> \A4SWIFT用户 * * 如果 A4SWIFT 用户组是域组。  
  
4.  在组或用户名称窗格中，选择**A4SWIFT 管理员**。 在权限窗格中，选择**允许**为**完全控制**。  
  
5.  在组或用户名称窗格中，选择**A4SWIFT 用户**。 在权限窗格中，单击**允许**为**读取和执行**，**列出文件夹内容**，和**读取**。  
  
6.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [疑难解答： 问题和解决方法](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)