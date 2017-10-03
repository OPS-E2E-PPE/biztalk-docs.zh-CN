---
title: "部署 Limitations2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deployment, limitations
- passwords, adapter limitations
ms.assetid: 9db2ca70-5db2-4b14-a898-13049737c188
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05fa9704823bd7e9df9f0bc7d4516719a8a490e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-limitations"></a>部署限制
传输适配器密码存储为星号 (\*\*\*\*\*\*)，由 BizTalk 部署向导，导出方法并传递到所管理绑定文件中在相同的格式中的组件。 在导入之前编辑绑定文件，将星号替换为随机的字母数字值（即，不替换为正确密码）。 然后输入正确的密码使用**传输属性**后导入绑定文件页。  
  
 在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。 这样可防止以明文形式显示密码信息。 下次使用文件导入绑定信息，你必须通过使用传输属性页用户界面中输入的密码。 或者，可以在导入前临时修改绑定文件，将密码输入到文件中。 在这种情况下，必须从绑定文件删除密码，导入操作成功完成后。  
  
> [!NOTE]
>  将 .msi 文件导入包含任何企业适配器的绑定信息的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序时，您可能会收到一条导入错误消息。 受支持的修补程序是可从 Microsoft 处的错误的完整说明以及[http://support.microsoft.com/kb/923733/en-us](http://support.microsoft.com/kb/923733/en-us)。  
  
## <a name="password-limitation-workaround"></a>密码限制的解决方法  
 使用以下方法之一作为密码限制的解决方法。  
  
#### <a name="to-work-around-the-password-limitation"></a>若要解决的密码限制  
  
1.  在导入之前编辑绑定文件，将星号替换为明文密码。  
  
    > [!CAUTION]
    >  出于安全考虑，这不被建议。  
  
2.  在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。 输入正确的密码使用**传输属性**后导入绑定文件页。  
  
    > [!NOTE]
    >  只有当目标计算机上安装了 Microsoft Visual Studio 或者开发一个自定义工具，才能使用这种解决方法。  
  
 **- 或 -**  
  
#### <a name="to-work-around-the-password-limitation"></a>若要解决的密码限制  
  
1.  使用企业单一登录，而不是使用密码。  
  
     使用的 SSO 选项需要在没有额外的工作;仅导入的绑定文件。  
  
2.  验证逻辑的系统和传输和接收服务。  
  
## <a name="see-also"></a>另请参阅  
 [如何设置博士 Edwards OneWorld 传输属性](../core/how-to-set-jd-edwards-oneworld-transport-properties.md)   
 [部署端口和程序集](../core/deploying-ports-and-assemblies4.md)