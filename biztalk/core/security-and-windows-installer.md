---
title: 安全性和 Windows 安装程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, Windows installer
- Windows installer
ms.assetid: efa68c3e-2006-4665-bd41-07defaf4e2e2
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9d452fc92e9fcd1c238086513a08b4b392caaa5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017519"
---
# <a name="security-and-windows-installer"></a>安全性和 Windows 安装程序
Windows Installer 是一种用于安装和更新 BizTalk 应用程序的强大工具。 使用 Windows Installer 时，应注意可能由恶意 Windows Installer (.msi) 文件创建者造成的安全问题，并应采取措施防止此类问题发生。  
  
 通常由管理员运行 .msi 文件，因而在安装和更新应用程序期间运行的进程具有非常高的权限。 恶意 .msi 文件创建者可以通过多种方式来利用此缺陷，其中包括：  
  
- 运行会对您的系统或文件进行非法更改的脚本文件。  
  
- 覆盖 COM 目录。  
  
- 覆盖注册表值。 不能回滚这些更改。  
  
- 填满整个文件系统。  
  
  处理 .msi 文件时，至少应采取以下防范措施：  
  
- 只安装完全信任的 .msi 文件。  
  
  > [!NOTE]
  >  作为一种最佳实践，负责生成 .msi 文件的人员应采取额外措施来对 .msi 文件进行签名，以便用户可以验证 .msi 文件的来源是否是可信的。  
  
- 在生产环境中使用 .msi 文件之前对其进行彻底测试。  
  
- 将 .msi 文件存储在用适当的随机访问控制列表 (DACL) 进行保护的文件夹中。  
  
## <a name="see-also"></a>请参阅  
 [应用程序部署的安全注意事项](../core/security-considerations-for-application-deployment.md)