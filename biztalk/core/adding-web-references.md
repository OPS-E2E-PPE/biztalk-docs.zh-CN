---
title: "添加 Web 引用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2cbf8cd4c21009190fc459312467656410dc663a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="adding-web-references"></a>添加 Web 引用
在添加 Web 端口之前，需要向 BizTalk 项目添加 Web 引用。 Web 引用是对可用于你的项目的 Web Services 的说明。 BizTalk 项目添加到你的项目的 Web 引用时，创建业务流程 Web 端口类型，Web 消息类型，（映射文件） Reference.map、 Reference.odx （orchestration 文件）、 \< *WebService*\>。disco （发现文件） 和\< *WebService*\>.wsdl （Web 服务描述语言文件） 到你的项目。 如果 Web Services 描述语言 (WSDL) 文件包含架构 Web 消息类型，则 BizTalk 项目会向你的项目添加 Reference.xsd。  
  
 Web 引用包括：  
  
-   Web Services 的统一资源定位符 (URL)。  
  
-   WSDL 文件，提供关于服务的信息，如可用方法、端口和消息类型等。  
  
-   引用映射 (Reference.map)。  
  
 添加 Web 引用时，该 Web Services 的所有 Web 方法必须与 BizTalk Server 兼容。 不能为 Web Services 中的特定 Web 方法指定条件属性。  
  
 通过将添加到你的项目的 Web 引用**添加 Web 引用**对话框。 有关如何添加 Web 引用的详细信息，请参阅[使用 Visual Studio](../core/using-visual-studio.md)。  
  
 如果你计划使用业务流程执行语言 (BPEL) 导出过程导出业务流程，则不能从现有的 BizTalk 项目引用 Web 引用。 如果从现有的 BizTalk 项目引用 Web 引用，BPEL 导出过程将自动生成第二个 WSDL 文件，并且将会丢失绑定信息。  
  
## <a name="see-also"></a>另请参阅  
 [创建 Web 端口](../core/creating-web-ports.md)   
 [使用 Web 服务](../core/consuming-web-services.md)