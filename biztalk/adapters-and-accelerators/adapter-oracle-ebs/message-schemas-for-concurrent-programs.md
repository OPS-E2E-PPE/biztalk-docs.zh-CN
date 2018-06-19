---
title: 并发程序的消息架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c5709d5-e2b3-485b-9cdd-004985972ba1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f475fce04e796e633359c846c339f521b6f74a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217229"
---
# <a name="message-schemas-for-concurrent-programs"></a>并发程序的消息架构
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]呈现作为操作的并发程序。 作为操作，公开的并发程序以及[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]还显示以下三个标准操作： Get_Status、 Wait_For_Request 和 Submit_Request。 有关这些操作与并发程序相关的信息，请参阅[并发程序上的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)。  
  
## <a name="message-structure-of-concurrent-program-operations"></a>消息结构的并发程序操作  
 对于并发程序中加以表示操作遵循请求-响应消息交换模式。 下表显示这些请求和响应消息的结构。  
  
> [!NOTE]
>  在表后，请参阅实体说明。  
  
|运算|XML 消息|Description|  
|---------------|-----------------|-----------------|  
|[Concurrent_Program_Name]请求|`<?xml version="1.0" encoding="utf-8" ?> <[Concurrent_Program_Name] xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]/">   <SetOptions>     <Implicit>[value]</Implicit>     <Protected>[value]</Protected>     <Language>[value]</Language>     <Territory>[value]</Territory>     <ContinueOnFail>[value]</ContinueOnFail>   </SetOptions>   <SetPrintOptions>     <Printer>[value]</Printer>     <Style>[value]</Style>     <Copies>[value]</Copies>     <SaveOutput>[value]</SaveOutput>     <PrintTogether>[value]</PrintTogether>     <ContinueOnFail>[value]</ContinueOnFail>   </SetPrintOptions>   <SetRepeatOptions>     <RepeatTime>[value]</RepeatTime>     <RepeatInterval>[value]</RepeatInterval>     <RepeatUnit>[value]</RepeatUnit>     <RepeatType>[value]</RepeatType>     <RepeatEndTime>[value]</RepeatEndTime>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRepeatOptions>   <Description>[value]</Description>   <StartTime><[value]</StartTime>   <[CONCURRENT_PROGRAM_ARGUMENT1]>[value]</[CONCURRENT_PROGRAM_ARGUMENT1]>   <[CONCURRENT_PROGRAM_ARGUMENT2]>[value]</[CONCURRENT_PROGRAM_ARGUMENT2]>   … </[Concurrent_Program_Name]>`|-[Concurrent_Program_Name] 操作采用标准的五个参数： *SetOptions*， *SetPrintOptions*， *SetRepeatOptions*，*说明*，和*StartTime*。<br /><br /> - *ContinueOnFail*参数指示是否并发请求提交应继续在用例中的父参数 (*SetOptions*， *SetPrintOptions*或*SetRepeatOptions*) 失败，或是否它应引发异常。 你可以指定**True** （继续） 或**False** （引发异常）。<br /><br /> -有关每个参数的详细信息，请参见[并发程序上的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)。|  
|[Concurrent_Program_Name]响应|`<?xml version="1.0" encoding="utf-8" ?> <[Concurrent_Program_Name]Response xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]">   <[Concurrent_Program_Name]Result>[value]</[Concurrent_Program_Name]Result> </[Concurrent_Program_Name]Response>`|来自 Oracle E-business Suite 的响应包含一个并发请求 id。|  
|Get_Status 请求|`<?xml version="1.0" encoding="utf-8" ?> <GetStatusForConcurrentProgram xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]">   <RequestId>[value]</RequestId>  </GetStatusForConcurrentProgram>`|此 Get_Status 请求消息使用并发程序的请求的 ID 作为输入。|  
|Get_Status 响应|`<?xml version="1.0" encoding="utf-8" ?> <GetStatusForConcurrentProgramResponse xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]">   <GetStatusForConcurrentProgramResult>[value]</GetStatusForConcurrentProgramResult>    <Phase>[value]</Phase>    <Status>[value]</Status>    <DevPhase>[value]</DevPhase>    <DevStatus>[value]</DevStatus>    <Message>[value]</Message>  </GetStatusForConcurrentProgramResponse>`|此 Get_Status 响应消息返回请求阶段/状态和并发程序完成消息。<br /><br /> 有关每个参数的详细信息，请参阅[并发程序上的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)。|  
|Wait_For_Request 请求|`<?xml version="1.0" encoding="utf-8" ?> <WaitForRequestForConcurrentProgram xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]">   <RequestId>[value]</RequestId>   <Interval>[value]</Interval>   <MaxWait>[value]</MaxWait>    </WaitForRequestForConcurrentProgram>`|有关每个参数的详细信息，请参阅[并发程序上的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)。|  
|Wait_For_Request 响应|`<?xml version="1.0" encoding="utf-8" ?> <WaitForRequestForConcurrentProgramResponse xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]">   <WaitForRequestForConcurrentProgramResult>[value]</WaitForRequestForConcurrentProgramResult>    <Phase>[value]</Phase>    <Status>[value]</Status>    <DevPhase>[value]</DevPhase>    <DevStatus>[value]</DevStatus>    <Message>[value]</Message>    </WaitForRequestForConcurrentProgramResponse>`|此 Wait_For_Request 响应消息返回请求阶段/状态和并发程序完成消息。<br /><br /> 有关每个参数的详细信息，请参阅[并发程序上的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)。|  
|Submit_Request 请求|`<?xml version="1.0" encoding="utf-8" ?> <SubmitRequestForConcurrentProgram xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]">   <SetOptions>     <Implicit>[value]</Implicit>     <Protected>[value]</Protected>     <Language>[value]</Language>     <Territory>[value]</Territory>     <ContinueOnFail>[value]</ContinueOnFail>   </SetOptions>   <SetPrintOptions>     <Printer>[value]</Printer>     <Style>[value]</Style>     <Copies>[value]</Copies>     <SaveOutput>[value]</SaveOutput>     <PrintTogether>[value]</PrintTogether>     <ContinueOnFail>[value]</ContinueOnFail>   </SetPrintOptions>   <SetRepeatOptions>     <RepeatTime>[value]</RepeatTime>     <RepeatInterval>[value]</RepeatInterval>     <RepeatUnit>[value]</RepeatUnit>     <RepeatType>[value]</RepeatType>     <RepeatEndTime>[value]</RepeatEndTime>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRepeatOptions>     <Program>[value]</Program>   <Description>[value]</Description>   <StartTime>[value]</StartTime>   <Arguments>[array_of_strings</Arguments>    </SubmitRequestForConcurrentProgram>`|有关每个参数的详细信息，请参阅[并发程序上的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)。|  
|Submit_Request 响应|`<?xml version="1.0" encoding="utf-8" ?> <SubmitRequestForConcurrentProgramResponse xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]">   <SubmitRequestForConcurrentProgramResult>[value]</SubmitRequestForConcurrentProgramResult>  </SubmitRequestForConcurrentProgramResponse>`|如果提交请求成功完成，响应消息返回并发请求 id。 否则，它将返回"0"。|  
  
 实体说明：  
  
 [VERSION] = http://schemas.microsoft.com/OracleEBS/2008/05  
  
 [APP_SHORT_NAME] = 应用程序短名称  
  
 [CONCURRENT_PROGRAM_ARGUMENT] = 预期并发程序不同，因为在 Oracle E-business Suite 中定义的自变量  
  
## <a name="message-actions-for-concurrent-programs"></a>消息操作的并发程序  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]对于并发程序使用以下的消息操作。  
  
> [!NOTE]
>  在表后，请参阅实体说明。  
  
|消息|操作|示例|  
|-------------|------------|-------------|  
|[Concurrent_Program_Name]请求|ConcurrentPrograms / [APP_SHORT_NAME] / [CONCURRENT_PROGRAM_SHORT_NAME]|ConcurrentPrograms/SQLGL/ADSFINS|  
|[Concurrent_Program_Name]响应|ConcurrentPrograms / [APP_SHORT_NAME] / [CONCURRENT_PROGRAM_SHORT_NAME] / 响应|ConcurrentPrograms/SQLGL/ADSFINS/响应|  
|Get_Status 请求|ConcurrentPrograms / [APP_SHORT_NAME] / GetStatusForConcurrentProgram|ConcurrentPrograms/SQLGL/GetStatusForConcurrentProgram|  
|Get_Status 响应|ConcurrentPrograms / [APP_SHORT_NAME] / GetStatusForConcurrentProgram/响应|ConcurrentPrograms/SQLGL/GetStatusForConcurrentProgram/响应|  
|Wait_For_Request 请求|ConcurrentPrograms / [APP_SHORT_NAME] / WaitForRequestForConcurrentProgram|ConcurrentPrograms/SQLGL/WaitForRequestForConcurrentProgram|  
|Wait_For_Request 响应|ConcurrentPrograms / [APP_SHORT_NAME] / WaitForRequestForConcurrentProgram/响应|ConcurrentPrograms/SQLGL/WaitForRequestForConcurrentProgram/响应|  
|Submit_Request 请求|ConcurrentPrograms / [APP_SHORT_NAME] / SubmitRequestForConcurrentProgram|ConcurrentPrograms/SQLGL/SubmitRequestForConcurrentProgram|  
|Submit_Request 响应|ConcurrentPrograms / [APP_SHORT_NAME] / SubmitRequestForConcurrentProgram/响应|ConcurrentPrograms/SQLGL/SubmitRequestForConcurrentProgram/响应|  
  
 实体说明：  
  
 [APP_SHORT_NAME] = 应用程序短名称  
  
 [CONCURRENT_PROGRAM_SHORT_NAME] = 并发程序短名称  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 Oracle E-business Suite 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)