---
title: 如何在主机上使用跟踪实用程序启动的 SSO |Microsoft 文档
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
ms.openlocfilehash: ebb2003cc6091e3f14bd863902e03649d9005722
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973451"
---
# <a name="how-to-use-the-trace-utility-in-host-initiated-sso"></a>如何在主机上使用跟踪实用程序启动的 SSO
故障排除的主要方法是跟踪。  
  
## <a name="tracing"></a>跟踪  
 使用 Trace 命令行实用工具在 SSO 中启用跟踪。  
  
> [!NOTE]
>  为了使 trace 命令起作用，文件 tracelog.exe 必须位于以下目录中：  
>   
>  \<*驱动器*\>: \program Files\Enterprise 单一登录  
  
> [!NOTE]
>  你可以从以下位置下载此文件： [http://go.microsoft.com/fwlink/?LinkId=59534](http://go.microsoft.com/fwlink/?LinkId=59534)  
  
#### <a name="to-use-the-trace-utility"></a>若要使用跟踪实用程序  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \program Files\Enterprise 单一登录。  
  
4.  类型**跟踪 – start – 高**若要将跟踪级别设置为高，并开始跟踪。  
  
5.  运行主机启动的 SSO 的方案。  
  
6.  类型**跟踪 – 停止**结束跟踪。 将在上述目录中生成 .bin 文件，可以将其发送到 Microsoft 以进行分析。  
  
## <a name="see-also"></a>另请参阅  
 [主机启动的 SSO](../core/host-initiated-sso.md)