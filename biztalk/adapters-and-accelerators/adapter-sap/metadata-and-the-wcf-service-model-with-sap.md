---
title: 元数据和 WCF 服务模型使用 SAP |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1900cf66-a0d0-46f4-896b-7f6de3b51875
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f120d2d93dcfe56595c020a4032c4d714afc5c90
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373192"
---
# <a name="metadata-and-the-wcf-service-model-with-sap"></a>元数据和具有 SAP 的 WCF 服务模型
在 WCF 服务模型，可使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel Metadata Utility Tool (svcutile.exe) 生成代理类通过它你代码可能是：  
  
- 调用适配器 （WCF 客户端类） 上的操作  
  
- 从适配器 （WCF 服务约定） 接收操作  
  
  这些工具生成表示目标操作 （以及支持消息协定、 操作约定和数据协定） 的服务约定的.NET 类公开的元数据从[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]。 了解此生成的代码的结构的帮助，请参阅[了解生成的客户端代码](https://msdn.microsoft.com/library/ms733881.aspx)。 本主题专门介绍代码 svcutil.exe 生成，但其内容也是适用于代码的[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。 有关如何生成 WCF 客户端类或 WCF 服务协定 （接口） 为目标的操作以及 svcutil.exe 之间的差异信息并[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[为 SAP 生成 WCF 客户端或 WCF 服务约定解决方案项目](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。  
  
## <a name="see-also"></a>请参阅  
[开发 SAP 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)