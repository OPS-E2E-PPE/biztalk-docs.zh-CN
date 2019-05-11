---
title: 环境变量如何指示部署状态 |Microsoft Docs
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
ms.openlocfilehash: 5fc27a85f36b83b3fd3c0bd782807fa4f5b73364
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387464"
---
# <a name="how-environment-variables-indicate-deployment-state"></a>环境变量如何指示部署状态
在调用之后，预处理或后处理脚本可以确定的部署状态 （安装、 导入、 删除、 卸载、 导入回滚或安装回滚） 正在运行的检查环境变量 BTAD_ChangeRequestAction、 BTAD_InstallMode和 BTAD_HostClass。  

 下表介绍指示不同的部署状态的三个变量的组合。  


|       部署状态        |     预期值      |
|-------------------------------|--------------------------|
|                               | BTAD_ChangeRequestAction |
| 导入不带覆盖标志 |          创建          |
|  导入带覆盖标志   |          Update          |
|            安装            |          Update          |
|           Uninstall           |          DELETE          |
|        导入回滚        |          DELETE          |
|       安装回滚        |          DELETE          |

## <a name="see-also"></a>请参阅  
 [使用预处理和后处理脚本自定义应用程序部署](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)   
 [BTAD_ChangeRequestAction](../core/btad-changerequestaction.md)   
 [BTAD_InstallMode](../core/btad-installmode.md)   
 [BTAD_HostClass](../core/btad-hostclass.md)