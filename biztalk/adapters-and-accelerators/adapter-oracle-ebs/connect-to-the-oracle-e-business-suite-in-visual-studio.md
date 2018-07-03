---
title: 连接到在 Visual Studio 中的 Oracle 电子商务套件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e290ea7e-03f3-49d4-9f18-1e539d727d9c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3be6f861e2346b4cc7d8ad29598d8efbc4707c76
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984270"
---
# <a name="connect-to-the-oracle-e-business-suite-in-visual-studio"></a>连接到在 Visual Studio 中的 Oracle 电子商务套件
本部分提供有关如何使用信息[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
- **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** 现已推出[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目。 您使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]为想要面向您的 BizTalk 解决方案中的操作生成消息架构 (Xsd)。 有关使用 BizTalk Server 开发解决方案的详细信息，请参阅[开发 BizTalk Server 应用程序](../../core/developing-biztalk-server-applications.md)。  
  
- **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** 现已推出[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目。 您使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]为想要面向您的 BizTalk 解决方案中的操作生成消息架构 (Xsd)。 有关使用 BizTalk Server 开发解决方案的详细信息，请参阅[开发 BizTalk Server 应用程序](../../core/developing-biztalk-server-applications.md)。  
  
  > [!NOTE]
  >  因为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开为 WCF 自定义绑定和 BizTalk 适配器，可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]从要连接到 Oracle E-business Suite 的 BizTalk 项目。  
  
- **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** 是在非 BizTalk 编程项目中可用。 您使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]开发使用 WCF 服务模型的解决方案时生成 WCF 客户端类或 WCF 服务回调接口。 有关使用 WCF 服务模型开发解决方案的详细信息，请参阅[开发 Oracle E-business Suite 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)。  
  
  若要使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，您必须首先连接到 Oracle E-business Suite。 所有三个方法所显示的对话框，您可以通过它来配置通过设置以下连接：  
  
- **连接参数**。 这些是用于生成连接 URI 的参数。 必须指定数据源 （Oracle net 服务名称）。  
  
- **用于 Oracle E-business Suite 的用户名称密码凭据**。 使用这些上进行身份验证，Oracle E-business Suite 时建立的连接。 必须指定用户名和密码。  
  
  > [!IMPORTANT]
  >  在此阶段，可用于 Oracle E-business Suite 或基础的 Oracle 数据库中指定的凭据。 若要连接，并生成元数据可以指定任何凭据。 但是，在执行时要调用 Oracle E-business Suite 项目的操作，您必须指定 Oracle E-business Suite 凭据，因为需要它们来设置你想要调用的 Oracle E-business Suite 应用程序的应用程序上下文。 有关设置应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
- **绑定属性**。 生成操作的元数据时，绑定属性是在设计时，即，可选的。 有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
  在最低限度上，配置到 Oracle 数据库连接时你只需指定绑定属性和连接参数，需要建立连接并会影响返回的元数据的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]操作你想要为目标。 但是，您还可能想要指定任何其他绑定属性和连接参数，将在运行时使用的值。 这是因为：  
  
- [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]从绑定属性和在配置连接时指定的连接参数创建 BizTalk 端口绑定文件并将此文件添加到你的项目。 更高版本，可以使用此绑定文件创建在端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关绑定文件的详细信息，请参阅[配置使用的 Oracle 数据库的端口绑定文件的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)。  
  
- [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]从绑定属性以及在配置连接时指定的连接属性创建 app.config 文件并在项目目录中将此文件。  
  

- [连接到 Oracle E-business Suite 在 Visual Studio 中使用添加适配器服务引用插件](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-ebs-in-visual-studio-using-add-adapter-service-reference.md)  
  
## <a name="see-also"></a>请参阅  
 [获取 Visual Studio 中的 Oracle E-business Suite 操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)