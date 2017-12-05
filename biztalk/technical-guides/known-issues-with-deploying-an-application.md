---
title: "部署应用程序的已知问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e5fb4f6-f9bd-4322-93f9-723e9e3c3317
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7fa139469ea8718c3d4430235ffb576195e67a7
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="known-issues-with-deploying-an-application"></a>部署应用程序的已知的问题
## <a name="deploying-a-biztalk-application"></a>部署 BizTalk 应用程序  
 **部署更新的应用程序需要更正的引用**  
  
 如果要部署一个全新的应用程序以替换现有的应用程序，必须更正其他应用程序与要替换的应用程序之间的所有引用。  
  
 **使用 Visual Studio 部署应用程序可以停止应用程序**  
  
> [!NOTE]  
>  我们建议你避免使用 Visual Studio 部署到生产环境的应用程序。  
  
 如果你使用 Visual Studio 部署到生产环境的应用程序并且重新启动主机实例选项部署应用程序，包括那些不与相关联时，则设置为 True 在项目属性中，所有主机实例将重新启动此应用程序。 这样会停止在本地计算机的任何主机实例上运行的所有其他应用程序。  
  
## <a name="adding-artifacts-to-a-biztalk-application"></a>将项目添加到 BizTalk 应用程序  
 **移动项目可以移动依赖关系**  
  
 当你将项目移到新的应用程序时，它在其具有依赖关系的任何其他项目也被移动，除非新的应用程序具有对包含已移动的项目取决于项目的应用程序的引用。 同样，与移动项目有依存关系的所有项目也会被移动，除非包含这些项目的应用程序具有对新应用程序的引用。 移动项目时，系统会显示一起移动的其他项目的列表。 有关移动项目的说明，请参阅[如何将项目移到不同的应用程序](http://go.microsoft.com/fwlink/?LinkId=154999)(http://go.microsoft.com/fwlink/?LinkId=154999)。  
  
## <a name="exporting-a-biztalk-application"></a>导出 BizTalk 应用程序  
 **安装 Windows Vista 上的.msi 文件时，可以显示不正确错误**  
  
 当安装.msi 程序包导出使用[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]在 BizTalk Server 中在 Windows Vista® 上运行，你可能会收到以下不正确的错误，"安装程序遇到意外的错误安装此包。 这可能表示此程序包有问题。 错误代码为 2869。” 若要更正此错误，首次导入包使用 BizTalk Server 和重新导出和安装包。  
  
## <a name="importing-a-biztalk-application"></a>导入 BizTalk 应用程序  
 **密码不会从绑定添加到应用程序的文件**  
  
 为安全起见，在导出应用程序的过程中，密码从应用程序绑定中删除。 不过，密码并未从已添加到应用程序的绑定文件中删除。 在导入应用程序后，您需要重新配置密码，以便应用程序可以正常运行。 可以通过编辑绑定文件或通过使用管理控制台执行此操作。 有关编辑绑定文件的详细信息，请参阅[自定义绑定文件](http://go.microsoft.com/fwlink/?LinkId=155000)(http://go.microsoft.com/fwlink/?LinkId=155000)。 有关配置的适配器的安全性的详细信息，请参阅[使用适配器](http://go.microsoft.com/fwlink/?LinkId=155001)(http://go.microsoft.com/fwlink/?LinkId=155001)。  
  
 **BizTalk Server 不会回滚已编写脚本的导入或安装**  
  
 如果导入失败，则 BizTalk Server 将回滚所有导入操作（自定义脚本执行的所有操作除外）。 这也是如此安装和卸载操作。  
  
 **缺失的架构可能不会报告导入后**  
  
 如果您在一个应用程序中为发送端口创建了筛选器，此应用程序使用另一个应用程序中的属性架构，然后将第一个应用程序导入到新 BizTalk 组中，则您将收到缺少架构的警告，并且在安装和启动该应用程序时筛选功能将无法正常运行。 解决这个问题的方法是：先导入包含该架构的应用程序，然后再安装不包含该架构的应用程序。  
  
## <a name="see-also"></a>另请参阅  
 [部署应用程序](../technical-guides/deploying-an-application.md)