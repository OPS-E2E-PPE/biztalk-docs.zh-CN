---
title: "部署 Limitations1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: deployment, limitations
ms.assetid: a984ccce-37b2-4738-b652-7232a18e0510
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e65fb1c1a1211865b07c3abb987f0a1d31fbfd69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-limitations"></a>部署限制
传输适配器密码存储为星号 (\*\*\*\*\*\*) 在绑定文件中，将导出由 BizTalk Server 中，并且它将传递给在同一个管理组件格式。 在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。 输入正确的密码使用**传输属性**在 BizTalk Server 管理控制台中导入的绑定文件后的页。  
  
 这是一项已知的缺限。 在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。 这样可防止以明文形式显示密码信息。 下一次使用该文件导入绑定信息时，必须使用传输属性页用户界面输入密码。 或者，可以在导入前临时修改绑定文件，将密码输入到文件中。 在这种情况下，必须在成功完成导入操作后从绑定文件中删除密码。  
  
> [!NOTE]
>  导入中的.msi 文件时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包含的任何企业适配器的绑定信息的应用程序可能会收到一条导入错误消息。 受支持的修补程序是可从 Microsoft 处的错误的完整说明以及[http://go.microsoft.com/fwlink/?LinkID=196087](http://go.microsoft.com/fwlink/?LinkID=196087)。  
  
## <a name="password-limitation-workaround"></a>密码限制的解决方法  
 若要解决此密码限制问题，可使用以下方法之一：  
  
-   在导入之前编辑绑定文件，将星号替换为明文密码。  
  
> [!CAUTION]
>  出于安全考虑，这不被建议。  
  
-   在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。 输入正确的密码使用**传输属性**在 BizTalk Server 管理控制台中导入的绑定文件后的页。  
  
> [!NOTE]
>  只有当目标计算机上安装了 Visual Studio 或者您开发了一个自定义工具时，才能使用这种解决方法。  
  
-   验证逻辑的系统和传输和接收服务。  
  
## <a name="see-also"></a>另请参阅  
 [部署端口和程序集](../core/deploying-ports-and-assemblies2.md)