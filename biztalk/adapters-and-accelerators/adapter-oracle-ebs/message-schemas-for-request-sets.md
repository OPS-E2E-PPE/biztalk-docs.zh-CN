---
title: 请求集的消息架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bba9677d-ee94-4da5-8611-b1e47f2f3798
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fd81ee75088b41a182c5a2aa675266420f8f32f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217093"
---
# <a name="message-schemas-for-request-sets"></a>请求集的消息架构
在 Oracle E-business Suite 中的 Oracle 应用程序中设置每个请求显示作为中的操作[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]。  
  
## <a name="message-structure-of-request-set-operation"></a>请求消息结构集的操作  
 针对请求集显示操作遵循请求-响应消息交换模式。 下表显示这些请求和响应消息的结构。  
  
> [!NOTE]
>  在表后，请参阅实体说明。  
  
|运算|XML 消息|Description|  
|---------------|-----------------|-----------------|  
|[Request_Set_Name]请求|`<?xml version="1.0" encoding="utf-8" ?> <[Request_Set_Name] xmlns="[VERSION]/RequestSets/[APP_SHORT_NAME]/">   <SetRelClassOptions>     <Application>[value]</Application>     <ClassName>[value]</ClassName>     <CancelOrHold>[value]</CancelOrHold>     <StaleDate>[value]</StaleDate>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRelClassOptions>   <SetPrintOptions>     <Printer>[value]</Printer>     <Style>[value]</Style>     <Copies>[value]</Copies>     <SaveOutput>[value]</SaveOutput>     <PrintTogether>[value]</PrintTogether>     <ContinueOnFail>[value]</ContinueOnFail>   </SetPrintOptions>   <SetRepeatOptions>     <RepeatTime>[value]</RepeatTime>     <RepeatInterval>[value]</RepeatInterval>     <RepeatUnit>[value]</RepeatUnit>     <RepeatType>[value]</RepeatType>     <RepeatEndTime>[value]</RepeatEndTime>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRepeatOptions>   <SetNlsOptions>     <Language>[value]</Language>     <Territory>[value]</Territory>     <ContinueOnFail>[value]</ContinueOnFail>   </SetNlsOptions>   <StartTime><[value]</StartTime>   <[CONCURRENT_PROGRAM_NAME1]>[value]</[CONCURRENT_PROGRAM_NAME1]>   <[CONCURRENT_PROGRAM_NAME2]>[value]</[CONCURRENT_PROGRAM_NAME2]>   … </[Request_Set_Name]>`|-[Request_Set_Name] 操作采用标准的五个参数： `SetRelClassOptions`， `SetPrintOptions`， `SetRepeatOptions`， `SetNlsOptions`，和`StartTime`。<br /><br /> -`ContinueOnFail`参数指示请求集提交是否应继续还是中引发异常用例 parent 参数 (`SetRelClassOptions`， `SetPrintOptions`，`SetRepeatOptions`或`SetNlsOptions`) 失败。 你可以指定**True** （继续） 或**False** （引发异常）。<br /><br /> -有关每个参数的详细信息，请参见[对请求设置的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)。|  
|[Request_Set_Name]响应|`<?xml version="1.0" encoding="utf-8" ?> <[Request_Set_Name]Response xmlns="[VERSION]/RequestSets/[APP_SHORT_NAME]">   <[Request_Set_Name]Result>[value]</[Request_Set_Name]Result> </[Request_Set_Name]Response>`|来自 Oracle E-business Suite 的响应包含一个并发请求 id。|  
  
 实体说明：  
  
 [VERSION] = http://schemas.microsoft.com/OracleEBS/2008/05  
  
 实例时都提供 SQL Server 登录名。  
  
 [CONCURRENT_PROGRAM_NAME] = 并发请求集中包含的程序。  
  
## <a name="message-actions-for-request-sets"></a>请求集的消息操作  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]请求集使用以下的消息操作。  
  
> [!NOTE]
>  在表后，请参阅实体说明。  
  
|消息|操作|示例|  
|-------------|------------|-------------|  
|请求 Set 请求|RequestSets / [APP_SHORT_NAME] / [REQUESTSET_SHORT_NAME]|RequestSets/SQLGL/FNDRSSUB965|  
|请求集响应|RequestSets / [APP_SHORT_NAME] / [REQUESTSET_SHORT_NAME]] / 响应|RequestSets/SQLGL/FNDRSSUB965/响应|  
  
 实体说明：  
  
 [APP_SHORT_NAME] = 应用程序短名称。  
  
 [REQUESTSET_SHORT_NAME] = 请求设置短名称。  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 Oracle E-business Suite 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)