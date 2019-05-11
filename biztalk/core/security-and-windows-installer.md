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
ms.openlocfilehash: fad36a25bac5d3319a55529cbedb02a5c5803070
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251116"
---
# <a name="security-and-windows-installer"></a>安全性和 Windows 安装程序
Windows 安装程序是用于安装和更新 BizTalk 应用程序的强大工具。 使用 Windows 安装程序，应注意的安全问题，可能由恶意 Windows Installer (.msi) 文件创建者和采取措施来阻止它们。  
  
 通常由管理员运行.msi 文件，因此在应用程序安装或更新过程中运行的进程具有非常高的权限。 恶意.msi 文件创建者可能会利用多种方式，包括以下这一事实：  
  
- 正在运行的系统或文件进行非法更改的脚本文件。  
  
- 覆盖 COM 目录。  
  
- 覆盖注册表值。 不能回滚这些更改。  
  
- 流量激增的文件系统。  
  
  当处理.msi 文件时，应至少采取以下预防措施：  
  
- 安装在完全信任的.msi 文件。  
  
  > [!NOTE]
  >  最佳做法是，负责生成.msi 文件的人员应采取额外措施，以便用户可以验证文件的源是受信任签名的.msi 文件。  
  
- 在生产环境中使用它们之前进行全面测试您的.msi 文件。  
  
- 将.msi 文件存储在使用适当的随机访问控制列表 (Dacl) 保护的受保护文件夹中。  
  
## <a name="see-also"></a>请参阅  
 [应用程序部署的安全注意事项](../core/security-considerations-for-application-deployment.md)