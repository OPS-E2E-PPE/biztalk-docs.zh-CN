---
title: 部署应用程序的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e5fb4f6-f9bd-4322-93f9-723e9e3c3317
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee4bc6f54ad0ce3c355d8d6aad9a09e24387ec7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395823"
---
# <a name="known-issues-with-deploying-an-application"></a>部署应用程序的已知的问题
## <a name="deploying-a-biztalk-application"></a>部署 BizTalk 应用程序  
 **部署更新的应用程序需要更正的引用**  
  
 如果部署全新的应用程序以替换现有应用程序，你必须更正其他应用程序以及要替换的应用程序之间的所有引用。  
  
 **使用 Visual Studio 部署应用程序，可以停止应用程序**  
  
> [!NOTE]  
>  我们建议您避免使用 Visual Studio 部署到生产环境的应用程序。  
  
 如果你使用 Visual Studio 部署到生产环境的应用程序并重新启动主机实例选项设置为在项目属性中，所有主机实例，则返回 True 部署包括那些不与相关联的应用程序时将重新启动此应用程序。 这将停止所有本地计算机上的任何主机实例运行其他应用程序。  
  
## <a name="adding-artifacts-to-a-biztalk-application"></a>将项目添加到 BizTalk 应用程序  
 **移动项目可以移动的依赖项**  
  
 当将项目移到新的应用程序时，它在其具有依赖关系的任何其他项目也被移动，除非新的应用程序具有对包含取决于移动的项目的项目的应用程序的引用。 此外，移动项目有依赖关系的任何项目也将被移动，除非其包含的应用程序具有对新应用程序的引用。 当移动项目，将向您显示一起移动的其他项目的列表。 有关移动项目的说明，请参阅[如何将项目移到不同的应用程序](http://go.microsoft.com/fwlink/?LinkId=154999)(http://go.microsoft.com/fwlink/?LinkId=154999)。  
  
## <a name="exporting-a-biztalk-application"></a>导出 BizTalk 应用程序  
 **安装 Windows Vista 上的.msi 文件时，可以显示不正确错误**  
  
 当使用安装.msi 程序包导出[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]Windows Vista® 上运行的 BizTalk Server，可能会收到以下错误，"安装程序遇到意外的错误安装此包。 这可能表示此软件包存在问题。 错误代码为 2869年。" 若要更正此错误，首先使用 BizTalk Server 将包导入然后重新导出并安装包。  
  
## <a name="importing-a-biztalk-application"></a>导入 BizTalk 应用程序  
 **密码不会从绑定文件添加到应用程序**  
  
 出于安全原因，在应用程序导出过程中不会保留密码从应用程序绑定。 它们不会但是，删除从绑定文件已添加到应用程序中。 在导入应用程序之后, 将需要重新配置密码，以便对函数应用程序。 可以通过编辑绑定文件或使用管理控制台执行此操作。 有关编辑绑定文件的详细信息，请参阅[自定义绑定文件](http://go.microsoft.com/fwlink/?LinkId=155000)(http://go.microsoft.com/fwlink/?LinkId=155000)。 有关配置适配器的安全性的详细信息，请参阅[使用适配器](http://go.microsoft.com/fwlink/?LinkId=155001)(http://go.microsoft.com/fwlink/?LinkId=155001)。  
  
 **BizTalk Server 不会回滚已编写脚本的导入或安装**  
  
 如果导入失败，BizTalk Server 将回滚所有导入操作除外自定义脚本执行的任何操作。 这也是如此的安装和卸载操作。  
  
 **缺少架构可能不会导入后报告**  
  
 如果一个应用程序在另一个应用程序中使用的属性架构中创建的发送端口的筛选器，然后将第一个应用程序导入新的 BizTalk 组，不会收到的警告，该架构缺少，并且筛选功能将不正常时安装和启动应用程序。 可以通过导入包含架构，然后再安装不包含架构的应用程序的应用程序来更正此问题。  
  
## <a name="see-also"></a>请参阅  
 [部署应用程序](../technical-guides/deploying-an-application.md)