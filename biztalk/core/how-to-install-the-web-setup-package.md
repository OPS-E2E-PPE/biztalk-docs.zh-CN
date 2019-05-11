---
title: 如何安装 Web 安装包 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, Web services
- Web services, deploying
- Web services, installing
ms.assetid: c6b38a2f-ad07-4ccd-b267-9e3510df88c3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb29badb7f3966a094b6131d7ecbf4fd41401116
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384877"
---
# <a name="how-to-install-the-web-setup-package"></a>如何安装 Web 安装包
使用分发文件夹的内容设置的目标计算机上的 Web 服务。  
  
### <a name="to-install-the-web-setup-package"></a>若要安装 Web 安装包  
  
1.  将复制到目标计算机上的分发文件夹。  
  
    > [!IMPORTANT]
    >  目标计算机必须安装的 BizTalk Server 运行时和必需的 BizTalk 程序集部署并安装在全局程序集缓存中。  
  
2.  运行。MSI 文件安装 Web 服务，然后按照安装向导会提示。  
  
    > [!IMPORTANT]
    >  当向导提示您为虚拟目录中删除"_Setup"后缀。删除后缀可确保接收位置地址与 Web 服务.asmx 文件匹配。  
  
3.  验证虚拟目录的安全设置正确进行授权。  
  
## <a name="see-also"></a>请参阅  
 [在无 Visual Studio 的计算机上部署已发布 Web 服务](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)