---
title: 添加 Web 引用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BPEL, orchestrations
- orchestrations, BPEL
- Web services, ports
- orchestrations, exporting
- Web services, projects
- Web services, references
- projects, Web services
ms.assetid: 7e40f215-f11a-4151-bcc6-e107bf36b6f6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32d6e2124598a97644036e309ce340eaf42ff8b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360851"
---
# <a name="adding-web-references"></a>添加 Web 引用
添加 Web 端口之前，需要将添加到 BizTalk 项目的 Web 引用。 Web 引用是可供你的项目的 Web 服务的说明。 BizTalk 项目时添加到你的项目的 Web 引用，请创建业务流程 Web 端口类型、 Web 消息类型、 Reference.map （映射文件）、 Reference.odx （业务流程文件） \< *WebService*\>。disco （发现文件），并\< *WebService*\>.wsdl （Web 服务描述语言文件） 到你的项目。 如果你的 Web 服务描述语言 (WSDL) 文件包含架构 Web 消息类型，BizTalk 项目向导向项目添加 Reference.xsd。  
  
 Web 引用包括：  
  
- Web 服务的通用资源定位器 (URL)。  
  
- WSDL 文件，提供有关可用的方法、 端口和消息类型等服务的信息。  
  
- 引用映射 (Reference.map)。  
  
  添加 Web 引用时，该 Web 服务的所有 Web 方法必须都是与 BizTalk Server 兼容。 Web 服务中，不能指定条件的特定 Web 方法属性。  
  
  使用添加到你的项目的 Web 引用**添加 Web 引用**对话框。 有关添加 Web 引用的详细信息，请参阅[使用 Visual Studio](../core/using-visual-studio.md)。  
  
  如果想要导出您的业务流程使用业务流程执行语言 (BPEL) 导出过程，您不能从现有的 BizTalk 项目引用 Web 引用。 如果从现有的 BizTalk 项目引用 Web 引用，BPEL 导出过程将自动生成第二个 WSDL 文件，并且将丢失绑定信息。  
  
## <a name="see-also"></a>请参阅  
 [创建 Web 端口](../core/creating-web-ports.md)   
 [使用 Web 服务](../core/consuming-web-services.md)