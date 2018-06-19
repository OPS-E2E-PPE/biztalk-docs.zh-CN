---
title: 环境变量如何指示部署状态 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scripts, variables
ms.assetid: 022b782b-008d-41a7-9880-d1c4e5e4015e
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 041e77eadb7c1b62e3441ee3b3c138203299f3a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246493"
---
# <a name="how-environment-variables-indicate-deployment-state"></a>环境变量如何指示部署状态
调用预处理脚本或后处理脚本时，脚本通过检查环境变量 BTAD_ChangeRequestAction、BTAD_InstallMode 和 BTAD_HostClass，可确定其所运行的部署状态（安装、导入、删除、卸载、导入回滚或安装回滚）。  
  
 下表说明了用来指示不同部署状态的三个变量的组合。  
  
|部署状态|预期值|  
|----------------------|---------------------|  
||BTAD_ChangeRequestAction|BTAD_InstallMode|BTAD_HostClass|  
|导入（不带覆盖标志）|创建|导入|ConfigurationDb|  
|导入（带覆盖标志）|Update|导入|ConfigurationDb|  
|Install|Update|Install|BizTalkHostInstance|  
|Uninstall|DELETE|Uninstall|BizTalkHostInstance|  
|导入回滚|DELETE|导入|ConfigurationDb|  
|安装回滚|DELETE|Install|BizTalkHostInstance|  
  
## <a name="see-also"></a>另请参阅  
 [前期和后期处理脚本用于自定义应用程序部署](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)   
 [BTAD_ChangeRequestAction](../core/btad-changerequestaction.md)   
 [BTAD_InstallMode](../core/btad-installmode.md)   
 [BTAD_HostClass](../core/btad-hostclass.md)