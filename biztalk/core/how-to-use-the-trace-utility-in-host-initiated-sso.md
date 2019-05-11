---
title: 如何在主机中使用跟踪实用工具启动的 SSO |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host initiated SSO, trace utility
- trace utility
ms.assetid: a53444d1-3f63-42a6-8ee6-b60ff9af9e41
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed0b0a77881cba6de26454f51c6f6f8e21103e90
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333173"
---
# <a name="how-to-use-the-trace-utility-in-host-initiated-sso"></a>如何在主机中使用跟踪实用工具启动的 SSO
故障排除的主要方法跟踪。  
  
## <a name="tracing"></a>跟踪  
 使用 Trace 命令行实用工具在 SSO 中启用跟踪。  
  
> [!NOTE]
>  Trace 命令起，文件 tracelog.exe 必须在以下目录中：  
>   
>  \<*驱动器*\>: \Program Files\Common Files\Enterprise Single Sign-on  
  
> [!NOTE]
>  可以从以下位置下载此文件： [http://go.microsoft.com/fwlink/?LinkId=59534](http://go.microsoft.com/fwlink/?LinkId=59534)  
  
#### <a name="to-use-the-trace-utility"></a>若要使用跟踪实用工具  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**Trace – start – high**将跟踪级别设置为高并开始跟踪。  
  
5.  运行方案中使用主机启动的 SSO。  
  
6.  类型**Trace – 停止**以结束跟踪。 在更高版本，您可以发送给 Microsoft 进行分析的目录中生成.bin 文件。  
  
## <a name="see-also"></a>请参阅  
 [主机启动的 SSO](../core/host-initiated-sso.md)