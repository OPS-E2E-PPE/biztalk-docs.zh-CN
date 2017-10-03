---
title: "部署 Limitations3 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passwords, deployment limitations
- deployment, password limitations
- transport adapter password
ms.assetid: 79cd330f-ecc5-430e-9d79-608593d873cb
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae0d01947e0769189c269a1853e7fda0e11cedb1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-limitations"></a>部署限制
传输适配器密码在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 导出的绑定文件中以星号 (******) 的形式进行存储，并且以同样的格式传递至管理组件。  
  
 在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。 这样可防止以明文形式显示密码信息。 下一次使用该文件导入绑定信息时，必须使用传输属性页用户界面输入密码。 或者，可以在导入前临时修改绑定文件，将密码输入到文件中。 在这种情况下，必须在完成导入操作后从绑定文件中删除密码。  
  
> [!NOTE]
>  在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序中导入包含针对任何企业适配器的绑定信息的 .msi 文件时，可能会收到一条导入错误消息。 受支持的修补程序是可从 Microsoft 处的错误的完整说明以及[http://go.microsoft.com/fwlink/?LinkID=196087](http://go.microsoft.com/fwlink/?LinkID=196087)。  
  
## <a name="password-limitation-workaround"></a>密码限制的解决方法  
 若要解决此密码限制问题，可使用以下方法之一：  
  
-   在导入之前编辑绑定文件，将星号替换为明文密码。  
  
    > [!CAUTION]
    >  出于安全考虑，不建议使用此方法。  
  
-   在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。 输入正确的密码使用**传输属性**在 BizTalk Server 管理控制台中导入的绑定文件后的页。  
  
    > [!NOTE]
    >  只有当目标计算机上安装了 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 或者您开发了一个自定义工具时，才能使用这种解决方法。  
  
 - 或 -  
  
-   使用企业单一登录 (SSO) 而不是使用密码。  
  
     使用 SSO 选项时需要导入绑定文件。  
  
 验证逻辑系统以及传输和接收服务。  
  
## <a name="see-also"></a>另请参阅  
 [部署端口和程序集](../core/deploying-ports-and-assemblies5.md)