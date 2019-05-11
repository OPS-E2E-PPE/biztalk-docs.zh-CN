---
title: 手动配置到 Oracle E-business 适配器的物理端口绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07369428-7b54-4d90-8c63-ba14e67fdbdd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6112aef168d95b396a123dc0775724c11a061e32
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375415"
---
# <a name="manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter"></a>手动配置到 Oracle E-business 适配器的物理端口绑定
本部分提供有关配置信息[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]作为 WCF 自定义绑定或通过使用 Wcf-oracleebs 端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 在部署后，适配器，您将能够发送和接收消息从 Oracle E-business Suite 使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 部署该适配器的步骤会有所不同，具体取决于：  
  
- 之间的通信方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 您可以选择配置发送、 接收、 发送-接收或发送接收端口。 下表总结了你的选择。  
  
  |端口方向|通信模式|可供选择的通信方向|  
  |--------------------|---------------------------|-----------------------------------------------|  
  |Send|单向|我将始终在发送消息此端口上。|  
  |Receive|单向|我始终将接收此端口上的消息。|  
  |发送接收|请求-响应|我将发送请求并接收响应。|  
  |接收发送|要求响应|我将接收请求并发送响应。|  
  
   有关详细信息，请参阅[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]帮助文档，网址[ http://go.microsoft.com/fwlink/?LinkID=101130 ](http://go.microsoft.com/fwlink/?LinkID=101130)。  
  
- 是否将适配器发送消息或接收来自 Oracle E-business Suite 的消息。 具体取决于是否想要发送或接收消息，将创建一个发送或接收端口，分别。  
  
  > [!NOTE]
  >  此外可以配置发送或接收端口通过导入创建的绑定配置文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]作为元数据生成的一部分。 有关使用此绑定文件配置端口的说明，请参阅[配置物理端口绑定使用端口绑定文件到 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [配置使用 WCF 自定义适配器和 Oracle E-business Suite 的端口](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-port-using-the-wcf-custom-adapter-and-oracle-e-business-suite.md)  
  
-   [配置使用 Wcf-oracleebs 适配器的端口](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-port-using-the-wcf-oracleebs-adapter.md)  
  
## <a name="see-also"></a>请参阅  
 [若要创建 Oracle E-business Suite 的应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)