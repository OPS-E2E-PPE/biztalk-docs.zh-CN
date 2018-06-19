---
title: BTAD_InstallDir |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTAD_InstallDir [environment variable]
ms.assetid: 3120f897-5501-4e99-8552-9d97e6314cd1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fc1a676248dedbfa28a8ec5721fe675e5e4dfd1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964723"
---
# <a name="btadinstalldir"></a>BTAD_InstallDir
BTAD_InstallDir 包含 BizTalk 应用程序的安装路径。 只有在操作为 Create 或 Update 且 BTAD_HostClass 是 BizTalkHostInstance 时，BTAD_InstallDir 才可用。  
  
## <a name="remarks"></a>注释  
 BTAD_InstallDir 设置为 Windows Installer 包的 TARGETDIR 属性。 默认值是通过 BizTalk %ProgramFiles%\Generated\\<*应用程序名称*\>。  
  
## <a name="see-also"></a>另请参阅  
 [前期和后期处理脚本环境变量](../core/pre-and-post-processing-script-environment-variables.md)   
 [环境变量如何指示部署状态](../core/how-environment-variables-indicate-deployment-state.md)   
 [如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)