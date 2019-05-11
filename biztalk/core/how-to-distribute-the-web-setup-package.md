---
title: 如何分发 Web 安装包 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, Web services
- Web services, distributing
- Web services, deploying
ms.assetid: 0db71fdf-80d9-4ad5-b0d4-730d0bb549d4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecffab64a02a8c42f7a50f2c87629aa1bf520662
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385171"
---
# <a name="how-to-distribute-the-web-setup-package"></a>如何分发 Web 安装包
创建安装包后，还需要创建一个分发文件夹以将 MSI 文件和 BindingInfo.xml 文件复制到其中来安装 Web Services。  
  
### <a name="to-distribute-the-web-setup-package"></a>分发 Web 安装包  
  
1.  创建一个分发文件夹以包含安装文件。  
  
2.  将 .MSI 文件从 Web 安装项目输出文件夹复制到该分发文件夹。  
  
3.  将 BindingInfo.xml 文件从 ASP.NET Web Services 项目文件夹中的临时文件夹复制到该分发文件夹。  
  
## <a name="see-also"></a>请参阅  
 [在无 Visual Studio 的计算机上部署已发布 Web 服务](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)