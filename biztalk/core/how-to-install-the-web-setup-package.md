---
title: "如何安装的 Web 安装程序包 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, Web services
- Web services, deploying
- Web services, installing
ms.assetid: c6b38a2f-ad07-4ccd-b267-9e3510df88c3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21fbacd76598a3a86cfa70b4761bc74420afe561
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-install-the-web-setup-package"></a>如何安装 Web 安装程序包
使用分发文件夹的内容在目标计算机上安装 Web Services。  
  
### <a name="to-install-the-web-setup-package"></a>安装 Web 安装包  
  
1.  将复制到目标计算机上的分发文件夹。  
  
    > [!IMPORTANT]
    >  目标计算机必须安装 BizTalk Server 运行时，并在全局程序集缓存中部署和安装了所需的 BizTalk 程序集。  
  
2.  运行。MSI 文件以安装 Web 服务然后按照安装向导会提示。  
  
    > [!IMPORTANT]
    >  当向导提示您输入虚拟目录时，请删除“_Setup”后缀，从而确保接收位置地址与 Web Services .asmx 文件匹配。  
  
3.  验证虚拟目录的安全设置是否正确，以便进行授权。  
  
## <a name="see-also"></a>另请参阅  
 [部署非 Visual Studio 计算机上的发布的 Web 服务](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)