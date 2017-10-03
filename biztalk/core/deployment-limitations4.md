---
title: "部署 Limitations4 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passwords, deployment limitations
- deployment, limitations
ms.assetid: 1312627e-9de2-461e-a8c4-66a9d41bb714
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2d8e33c7274ab0f95c6d7fff1bf9746ac86e420
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-limitations"></a>部署限制
传输适配器密码为星号 （*） 存储在由导出绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并将它传递给相同的格式中的管理组件。 在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。  
  
 在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。 这样可防止以明文形式显示密码信息。 下次使用文件导入绑定信息，你必须通过使用传输属性页用户界面中输入的密码。  
  
 或者，可以在导入前临时修改绑定文件，将密码输入到文件中。 在这种情况下，必须从绑定文件删除密码，导入操作成功完成后。  
  
> [!NOTE]
>  在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序中导入包含针对任何企业适配器的绑定信息的 .msi 文件时，可能会收到一条导入错误消息。 受支持的修补程序是可从 Microsoft 处的错误的完整说明以及[http://go.microsoft.com/fwlink/?LinkId=196087](http://go.microsoft.com/fwlink/?LinkId=196087)。  
  
## <a name="password-limitation-workaround"></a>密码限制的解决方法  
 若要解决此密码限制问题，您可以执行以下操作。  
  
#### <a name="to-work-around-the-password-limitation"></a>若要解决的密码限制  
  
1.  使用企业单一登录，而不是使用密码。 使用的 SSO 选项需要在没有额外的工作;仅导入的绑定文件。  
  
2.  验证逻辑的系统和传输和接收服务。  
  
## <a name="see-also"></a>另请参阅  
 [部署端口和程序集](../core/deploying-ports-and-assemblies3.md)