---
title: "元数据和 WCF 服务模型与 SAP |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1900cf66-a0d0-46f4-896b-7f6de3b51875
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f06cd33c0776df70e5ff2554d355915908012abb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="metadata-and-the-wcf-service-model-with-sap"></a>元数据和 WCF 服务模型与 SAP
在 WCF 服务模型中，你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutile.exe) 生成代理类通过其代码可以：  
  
-   调用适配器 （WCF 客户端类） 上的操作  
  
-   从适配器 （WCF 服务协定） 接收操作  
  
 这些工具生成表示服务协定的操作 （以及支持消息协定、 操作协定和数据协定） 的.NET 类公开的元数据从[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]。 了解此生成的代码的结构的帮助，请参阅[了解生成的客户端代码](https://msdn.microsoft.com/library/ms733881.aspx)。 本主题专门介绍 svcutil.exe 生成，但其内容也是适用于代码的代码，[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。 有关如何生成 WCF 客户端类或 WCF 服务协定 （接口） 为目标操作以及 svcutil.exe 之间的差异信息和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[为 SAP 生成 WCF 客户端或 WCF 服务协定解决方案项目](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。  
  
## <a name="see-also"></a>另请参阅  
[开发使用 WCF 服务模型的 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)