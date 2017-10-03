---
title: "业务流程引擎的运行时验证 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, assemblies
- orchestrations, validating
- validating, orchestration engine
- schemas, validating
- correlations, validating
- validating, schemas
- orchestration engine, runtime validation
- assemblies, validating
- validating, correlations
- validating, orchestrations
- validating
ms.assetid: f6085889-05d6-4eba-a528-9d034c4e4225
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e53adb5aa42c7dfe23df50707754bde200ea838a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="runtime-validation-for-the-orchestration-engine"></a>业务流程引擎的运行时验证
您可以配置业务流程引擎，使其执行各种运行时验证，这些验证可帮助您测试业务流程并诊断可能出现的配置错误或数据错误。  
  
 您可以在 BTSNTSvc.exe.config 中设置标志。BTSNTSvc.exe.config 是一个配置文件，您可以在 BTSNTSvc.exe 所在的目录（通常在 BizTalk 部署目录中）中创建或编辑该文件。 可以在 BTSNTSvc.exe.config 文件中设置以下标志：  
  
-   如果你设置**ValidateAssemblies**标志切换为`True`，引擎将尝试加载所有程序集引用的业务流程的和失败将引发时的即时依赖程序集Microsoft.XLANGs.Core.AssemblyValidationException。  
  
-   如果你设置**ValidateSchemas**标志切换为`True`，引擎使用 System.Xml.XmlValidatingReader 来验证每个表示消息部件类型的架构和在失败时引发 System.Xml.XmlException。  
  
-   如果你设置**ValidateCorrelations**标志切换为`True`，引擎验证，并行护航队列之一接收该匹配项具有相同的相关属性值，并在失败时引发的所有消息Microsoft.XLANGs.Core.CorrelationValidationException。  
  
-   如果你设置**ExtendedLogging**标志切换为`True`，引擎 Microsoft.XLANGs.BaseTypes.PublishMessageException 未能发布它的消息的信息中显示的提升的属性。  
  
 如果要禁用验证，请从配置文件中完全删除标志。 所有验证都启用时，引擎将验证程序集、架构和相关。 有关详细信息和 BTSNTSvc.exe.config 的示例，请参阅[业务流程引擎配置](../core/orchestration-engine-configuration.md)。  
  
## <a name="validate-assemblies"></a>验证程序集  
 业务流程引擎将验证业务流程引用的所有程序集是否可用。 为了使验证成功，在激活业务流程的第一个实例时，所有引用的程序集都必须在全局程序集缓存 (GAC) 中。 如果验证失败，则将在应用程序日志中记录错误并挂起业务流程。  
  
## <a name="validate-schemas"></a>验证架构  
 只要分配了 XSD 部分，业务流程引擎就会针对其架构验证该部分的数据。 如果验证失败，则将在应用程序日志中记录错误并引发异常。  
  
## <a name="validate-correlation"></a>验证相关  
 业务流程引擎将确认：为具有给定业务流程实例的相关指定的属性值反映在从该业务流程实例发送的所有消息中。 如果**validateCorrelation**未设置，引擎将假定发送的消息包含正确的相关值，并将执行任何检查。  
  
 如果任何相关验证失败，则引擎将在应用程序日志中记录错误，并引发类型的异常**CorrelationValidationException**。  
  
 默认情况下， **validateCorrelation**未设置。  
  
## <a name="see-also"></a>另请参阅  
 [调试业务流程](../core/debugging-orchestrations.md)   
 [业务流程引擎配置](../core/orchestration-engine-configuration.md)