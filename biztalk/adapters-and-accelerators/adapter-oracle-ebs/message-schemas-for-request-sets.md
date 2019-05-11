---
title: 请求集的消息架构 |Microsoft Docs
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
ms.openlocfilehash: 1fb14d8ed93f61f72b08bc4db31464bcf8eb4561
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530687"
---
# <a name="message-schemas-for-request-sets"></a>请求集的消息架构
在 Oracle E-business Suite 中的 Oracle 应用程序中设置每个请求显示在操作的形式[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]。  
  
## <a name="message-structure-of-request-set-operation"></a>请求的消息结构设置操作  
 提供的请求集的操作遵循请求-响应消息交换模式。 下表显示了这些请求和响应消息的结构。  
  
> [!NOTE]
>  实体说明表后进行查看。  
  
|操作|XML 消息|Description|  
|---------------|-----------------|-----------------|  
|[Request_Set_Name] Request|`<?xml version="1.0" encoding="utf-8" ?> <[Request_Set_Name] xmlns="[VERSION]/RequestSets/[APP_SHORT_NAME]/">   <SetRelClassOptions>     <Application>[value]</Application>     <ClassName>[value]</ClassName>     <CancelOrHold>[value]</CancelOrHold>     <StaleDate>[value]</StaleDate>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRelClassOptions>   <SetPrintOptions>     <Printer>[value]</Printer>     <Style>[value]</Style>     <Copies>[value]</Copies>     <SaveOutput>[value]</SaveOutput>     <PrintTogether>[value]</PrintTogether>     <ContinueOnFail>[value]</ContinueOnFail>   </SetPrintOptions>   <SetRepeatOptions>     <RepeatTime>[value]</RepeatTime>     <RepeatInterval>[value]</RepeatInterval>     <RepeatUnit>[value]</RepeatUnit>     <RepeatType>[value]</RepeatType>     <RepeatEndTime>[value]</RepeatEndTime>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRepeatOptions>   <SetNlsOptions>     <Language>[value]</Language>     <Territory>[value]</Territory>     <ContinueOnFail>[value]</ContinueOnFail>   </SetNlsOptions>   <StartTime><[value]</StartTime>   <[CONCURRENT_PROGRAM_NAME1]>[value]</[CONCURRENT_PROGRAM_NAME1]>   <[CONCURRENT_PROGRAM_NAME2]>[value]</[CONCURRENT_PROGRAM_NAME2]>   … </[Request_Set_Name]>`|-[Request_Set_Name] 操作采用标准的五个参数： `SetRelClassOptions`， `SetPrintOptions`， `SetRepeatOptions`， `SetNlsOptions`，和`StartTime`。<br /><br /> -`ContinueOnFail`参数指示是否应继续还是中引发异常用例的父参数集提交请求 (`SetRelClassOptions`， `SetPrintOptions`，`SetRepeatOptions`或`SetNlsOptions`) 失败。 您可以指定 **，则返回 True** （继续） 或**False** （引发异常）。<br /><br /> -对于每个参数的详细信息，请参阅[请求集的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)。|  
|[Request_Set_Name]响应|`<?xml version="1.0" encoding="utf-8" ?> <[Request_Set_Name]Response xmlns="[VERSION]/RequestSets/[APP_SHORT_NAME]">   <[Request_Set_Name]Result>[value]</[Request_Set_Name]Result> </[Request_Set_Name]Response>`|来自 Oracle E-business Suite 的响应包含并发请求 id。|  
  
 实体说明：  
  
 [VERSION] = http://schemas.microsoft.com/OracleEBS/2008/05  
  
 .  
  
 [CONCURRENT_PROGRAM_NAME] = 请求集中包含的并发程序。  
  
## <a name="message-actions-for-request-sets"></a>请求集的消息操作  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]请求集的使用以下的消息操作。  
  
> [!NOTE]
>  实体说明表后进行查看。  
  
|消息|操作|示例|  
|-------------|------------|-------------|  
|请求集请求|RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]|RequestSets/SQLGL/FNDRSSUB965|  
|请求集响应|RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]]/response|RequestSets/SQLGL/FNDRSSUB965/response|  
  
 实体说明：  
  
 [APP_SHORT_NAME] = 应用程序的短名称。  
  
 [REQUESTSET_SHORT_NAME] = 请求设置短名称。  
  
## <a name="see-also"></a>请参阅  
 [消息和用于 Oracle E-business Suite 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)