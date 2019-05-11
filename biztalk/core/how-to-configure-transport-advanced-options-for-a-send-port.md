---
title: 如何配置传输高级选项的发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, transport options [send ports]
- configuring, send ports
- send ports, transport options
- managing [send ports], configuring
- managing [send ports], transport options
ms.assetid: b0033e09-3c18-4e53-a470-e12978e61ba1
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86c61a7d77b3fbb4ebda539863223fa4ae12ed51
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340157"
---
# <a name="how-to-configure-transport-advanced-options-for-a-send-port"></a>如何配置传输高级选项的发送端口
使用 BizTalk Server 管理控制台来配置传输高级选项的发送端口。 这些选项确定的发送端口，例如的次数重试发送消息失败的消息和端口的服务时段计划如何处理消息。  
  
> [!NOTE]
> **从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，可以启用按序的送达的动态发送端口，具体取决于相应适配器类型。 此选项才可用的适配器类型对于静态发送端口，如文件适配器或 FTP 适配器能保证按序的送达的位置。
> 
> 六个消息，请考虑：M1、 M2、 M3，M4、 M5 和 M6。 M1，M3，M5 意为文件位置。 M2、 M4 和 M6 用于 FTP。 按序的送达动态发送端口可确保，M1、 M3 和 M5 进行排序;和 M2、 M4 和 M6 分别进行排序。 
> 
> 对于这些不支持按序的送达的适配器类型，不存在任何可配置的动态发送端口属性。 在运行时自动确定其传输选项。  
> 
> **对于以前的 BizTalk 版本**使用动态端口，没有可用于配置，因为在运行时自动确定传输选项的任何属性。

  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="controlling-send-port-priority"></a>控制发送端口的优先级  
 传输高级选项的优先级设置控制在其中可以从消息框中删除消息的顺序。 将具有较低的优先级，使较高优先级的端口更重要的相对于其他发送端口在单个主机端口更早处理具有较高优先级的端口。  
  
 优先级是在需要低响应时间对于某些类型的请求方案中有用。 例如，如果有多个发送端口连接到不同的系统来处理正常请求和交互式请求。 交互式请求要求响应时间短，因此，当提交交互式请求时，你想要确保尽可能快地处理。  
  
 BizTalk Server 不会尝试会公平对待各个消息的处理具有不同优先级的消息框中。 如果相等具有两个不同的优先级处理时在消息框中的项的数字开始，将项的较低优先级处理项都得到处理仅所有高优先级。 如果高优先级的项量大，就可以永远不会处理优先级较低的项。 换而言之，低优先级的项会出现资源不足。  
  
> [!WARNING]
>  为了尽量降低消息资源不足的风险，全面测试实际负载下的应用程序，以确保所有消息进行都处理。 故障来测试你的解决方案可能会导致未处理消息。  
  
 在内部，BizTalk Server 将优先级分配给每个订阅。 优先级可以是从 1 （最高优先级） 到 10 （优先级最低） 任何数字。 默认优先级为 7 来激活订阅和 5 相关订阅的因为关联消息将被传送早于激活订阅。  
  
## <a name="configure-the-transport-options"></a>配置传输选项 
  
1.  打开 **“BizTalk Server 管理”**。  
  
2.  展开 BizTalk 组，然后展开 BizTalk 应用程序。  
  
3.  选择**发送端口**，右键单击发送端口以配置，然后选择**属性**。  
  
4.  在左窗格中，选择**传输高级选项**。  
  
5.  下表中所述配置传输选项，然后选择**确定**。  仅以下属性中的一些适用于动态发送端口。
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**重试次数**|指定的发送端口以重新发送消息失败的消息的次数。 默认值为 3;允许的范围是从 0 到 1000。|  
    |**重试间隔**|指定以分钟为单位次重发消息尝试之间的间隔。 默认值为 5;允许的范围是从 0 到 525600。|  
    |**Priority**|设置重发尝试的优先级。|  
    |**按序的送达**|选择此复选框可按接收顺序发送消息。|  
    |**停止发送随后的消息当前消息失败**|选择此复选框可以停止发送随后失败消息的消息。 此选项是时才可用**按序送达**选择选项。|  
    |**为失败消息启用路由功能**|选择此选项可为失败消息启用路由功能。|  
    |**启用服务时段**|选择此选项可指定在此期间发送端口将操作通过指定开始时间和停止时间每一天的时间段。|  
    |**开始时间**|指定发送端口开始发送消息的每一天的时间。 此选项是时才可用**启用服务时段**选择选项。|  
    |**停止时间**|指定发送端口停止发送消息的每一天的时间。 此选项是时才可用**启用服务时段**选择选项。|  
  
## <a name="see-also"></a>请参阅  
[按序送达消息](../core/ordered-delivery-of-messages.md)  
 [创建和配置发送端口](../core/creating-and-configuring-send-ports.md)