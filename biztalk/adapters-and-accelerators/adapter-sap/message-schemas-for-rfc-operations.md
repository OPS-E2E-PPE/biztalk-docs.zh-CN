---
title: RFC 操作的消息架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RFC operations, message structure for
- RFC operations, message actions for
ms.assetid: 50cd9b28-2e66-4c76-9d19-f0da6e7b8e10
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccc0e3c37ab74e4682c0eaa209580507ba7628c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373216"
---
# <a name="message-schemas-for-rfc-operations"></a><span data-ttu-id="3c931-102">RFC 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="3c931-102">Message Schemas for RFC Operations</span></span>
<span data-ttu-id="3c931-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]作为操作的图面 SAP 远程函数调用 (RFC)。</span><span class="sxs-lookup"><span data-stu-id="3c931-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] surfaces SAP Remote Function Calls (RFC) as operations.</span></span> <span data-ttu-id="3c931-104">本主题包含有关消息架构和使用 RFC 操作的消息操作的信息。</span><span class="sxs-lookup"><span data-stu-id="3c931-104">This topic contains information about the message schemas and message actions used for RFC operations.</span></span> <span data-ttu-id="3c931-105">消息结构是相同的入站和出站 RFC 操作。</span><span class="sxs-lookup"><span data-stu-id="3c931-105">The message structure is the same for inbound and outbound RFC operations.</span></span> <span data-ttu-id="3c931-106">适配器支持 RFC 操作的概述，请参阅[Rfc 在 SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="3c931-106">For an overview of the RFC operations that the adapter supports, see [Operations on RFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md).</span></span>  

 <span data-ttu-id="3c931-107">此外可以在适配器上的 RFC 操作作为调用 Bapi。</span><span class="sxs-lookup"><span data-stu-id="3c931-107">You can also invoke BAPIs as RFC operations on the adapter.</span></span> <span data-ttu-id="3c931-108">本主题中包含此类调用的消息结构的示例。</span><span class="sxs-lookup"><span data-stu-id="3c931-108">An example of the message structure for such an invocation is included in this topic.</span></span>  

## <a name="message-structure-for-rfc-operations"></a><span data-ttu-id="3c931-109">RFC 操作的消息结构</span><span class="sxs-lookup"><span data-stu-id="3c931-109">Message Structure for RFC Operations</span></span>  
 <span data-ttu-id="3c931-110">下表显示了 RFC 消息架构。</span><span class="sxs-lookup"><span data-stu-id="3c931-110">The following table shows the RFC message schemas.</span></span> <span data-ttu-id="3c931-111">每个 RFC 操作包含请求消息和答复 （响应） 消息。</span><span class="sxs-lookup"><span data-stu-id="3c931-111">Each RFC operation consists of a request message and a reply (response) message.</span></span>  


|                             <span data-ttu-id="3c931-112">消息</span><span class="sxs-lookup"><span data-stu-id="3c931-112">Message</span></span>                              |                                                                                                                                                                                                                         <span data-ttu-id="3c931-113">XML 消息结构</span><span class="sxs-lookup"><span data-stu-id="3c931-113">XML Message Structure</span></span>                                                                                                                                                                                                                          |                                                                                                                                                                                                     <span data-ttu-id="3c931-114">Description</span><span class="sxs-lookup"><span data-stu-id="3c931-114">Description</span></span>                                                                                                                                                                                                      |
|------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                   <span data-ttu-id="3c931-115">RFC</span><span class="sxs-lookup"><span data-stu-id="3c931-115">RFC</span></span><br /><br /> <span data-ttu-id="3c931-116">([RFC_NAME])</span><span class="sxs-lookup"><span data-stu-id="3c931-116">([RFC_NAME])</span></span>                   | `<[RFC_NAME] xmlns="[VERSION]/Rfc/">   <IN1_PARAM_NAME>v1</IN1_PARAM_NAME>   <IN2_PARAM_NAME>v2</IN2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[RFC_NAME]>` |                                                                                              <span data-ttu-id="3c931-117">调用上的 SAP 系统的 RFC。</span><span class="sxs-lookup"><span data-stu-id="3c931-117">Invoke an RFC on the SAP system.</span></span><br /><br /> <span data-ttu-id="3c931-118">-导入，更改，并支持表参数。</span><span class="sxs-lookup"><span data-stu-id="3c931-118">- Import, changing, and table parameters are supported.</span></span><br /><br /> <span data-ttu-id="3c931-119">-导入并更改参数可以为 SAP 结构类型、 SAP 表类型或 SAP 简单数据类型。</span><span class="sxs-lookup"><span data-stu-id="3c931-119">- Import and changing parameters can be of SAP STRUCTURE TYPES, SAP TABLE TYPES or SAP simple data types.</span></span>                                                                                              |
|                <span data-ttu-id="3c931-120">RFC 响应 （[RFC_NAME] 响应）</span><span class="sxs-lookup"><span data-stu-id="3c931-120">RFC Response ([RFC_NAME]Response)</span></span>                 |     `<[RFC_NAME]Response xmlns="[VERSION]/Rfc/">   <OUT1_PARAM_NAME>v1</OUT1_PARAM_NAME>   <OUT2_PARAM_NAME>v2</OUT2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME>     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[RFC_NAME]Response>`      | <span data-ttu-id="3c931-121">RFC 返回。</span><span class="sxs-lookup"><span data-stu-id="3c931-121">RFC return.</span></span><br /><br /> <span data-ttu-id="3c931-122">-导出，更改，并支持表参数。</span><span class="sxs-lookup"><span data-stu-id="3c931-122">- Export, changing, and table parameters are supported.</span></span><br /><br /> <span data-ttu-id="3c931-123">**注意：** 默认情况下，响应消息中不显示表参数。</span><span class="sxs-lookup"><span data-stu-id="3c931-123">**Note:** By default, table parameters are not surfaced in the response message.</span></span> <span data-ttu-id="3c931-124">如果您需要在响应消息中的表参数，您必须在请求消息中传递空表参数。</span><span class="sxs-lookup"><span data-stu-id="3c931-124">If you require table parameters in response message, you must pass empty table parameters in the request message.</span></span><br /><br /> <span data-ttu-id="3c931-125">-导入并更改参数可以为 SAP 结构类型、 SAP 表类型或 SAP 简单数据类型。</span><span class="sxs-lookup"><span data-stu-id="3c931-125">- Import and changing parameters can be of SAP STRUCTURE TYPES, SAP TABLE TYPES or SAP simple data types.</span></span> |
|         <span data-ttu-id="3c931-126">RfcGetAttributes</span><span class="sxs-lookup"><span data-stu-id="3c931-126">RfcGetAttributes</span></span><br /><br /> <span data-ttu-id="3c931-127">(RfcGetAttributes)</span><span class="sxs-lookup"><span data-stu-id="3c931-127">(RfcGetAttributes)</span></span>          |                                                                                                                                                                                                                `<RfcGetAttributes> </RfcGetAttributes>`                                                                                                                                                                                                                |                                                  <span data-ttu-id="3c931-128">RfcGetAttributes 是 RFC SDK API 操作显示的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3c931-128">RfcGetAttributes is an RFC SDK API operation that is surfaced by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="3c931-129">RfcGetAttributes 操作允许一个客户端程序来检索语言、 系统 ID 和与 RFC 连接相关联的合作伙伴代码页。</span><span class="sxs-lookup"><span data-stu-id="3c931-129">The RfcGetAttributes operation enables a client program to retrieve the language, the system ID, and the partner code page that are associated with the RFC connection.</span></span>                                                   |
| <span data-ttu-id="3c931-130">RfcGetAttributes Response</span><span class="sxs-lookup"><span data-stu-id="3c931-130">RfcGetAttributes Response</span></span><br /><br /> <span data-ttu-id="3c931-131">(RfcGetAttributesResponse)</span><span class="sxs-lookup"><span data-stu-id="3c931-131">(RfcGetAttributesResponse)</span></span> |                                                                                                                                                          `<RfcGetAttributesResponse>   <Language>lang</Language>   <SysId>id</SysId>   <PartnerCodePage>pnrcp</PartnerCodePage> </RfcGetAttributesResponse>`                                                                                                                                                           |                                                                                                                              <span data-ttu-id="3c931-132">RfcGetAttributes 操作的响应返回的语言、 系统 ID 和与 RFC 连接相关联的合作伙伴代码页。</span><span class="sxs-lookup"><span data-stu-id="3c931-132">The response to the RfcGetAttributes operation returns the language, the system ID, and the partner code page that are associated with the RFC connection.</span></span>                                                                                                                              |

 <span data-ttu-id="3c931-133">[VERSION] = 消息版本字符串;例如， http://Microsoft.LobServices.SAP/2007/03。</span><span class="sxs-lookup"><span data-stu-id="3c931-133">[VERSION] = The message version string; for example, http://Microsoft.LobServices.SAP/2007/03.</span></span>  

 <span data-ttu-id="3c931-134">[RFC_NAME] = RFC; 的名称例如，RFC_CUSTOMER_GET。</span><span class="sxs-lookup"><span data-stu-id="3c931-134">[RFC_NAME] = Name of the RFC; for example, RFC_CUSTOMER_GET.</span></span>  

 <span data-ttu-id="3c931-135">[IN_PARAM_NAME] = RFC 导入参数的名称。</span><span class="sxs-lookup"><span data-stu-id="3c931-135">[IN_PARAM_NAME] = The name of an RFC Import parameter.</span></span>  

 <span data-ttu-id="3c931-136">[OUT_PARAM_NAME] = RFC 导出参数的名称。</span><span class="sxs-lookup"><span data-stu-id="3c931-136">[OUT_PARAM_NAME] = The name of an RFC Export parameter.</span></span>  

 <span data-ttu-id="3c931-137">[INOUT_PARAM_NAME] = RFC 更改参数的名称。</span><span class="sxs-lookup"><span data-stu-id="3c931-137">[INOUT_PARAM_NAME] = The name of an RFC Changing parameter.</span></span>  

 <span data-ttu-id="3c931-138">[TABLE_PARAM_NAME] = RFC 表参数的名称。</span><span class="sxs-lookup"><span data-stu-id="3c931-138">[TABLE_PARAM_NAME] = The name of an RFC Table parameter.</span></span>  

 <span data-ttu-id="3c931-139">[STRUCT_PARAM_NAME] = RFC 结构参数的名称。</span><span class="sxs-lookup"><span data-stu-id="3c931-139">[STRUCT_PARAM_NAME] = The name of an RFC Structure parameter.</span></span>  

## <a name="message-actions-for-rfc-operations"></a><span data-ttu-id="3c931-140">RFC 操作的消息操作</span><span class="sxs-lookup"><span data-stu-id="3c931-140">Message Actions for RFC Operations</span></span>  
 <span data-ttu-id="3c931-141">下表显示了 RFC 操作的消息操作。</span><span class="sxs-lookup"><span data-stu-id="3c931-141">The following table shows the message actions for RFC operations.</span></span>  


|         <span data-ttu-id="3c931-142">操作</span><span class="sxs-lookup"><span data-stu-id="3c931-142">Operation</span></span>         |           <span data-ttu-id="3c931-143">消息操作</span><span class="sxs-lookup"><span data-stu-id="3c931-143">Message Action</span></span>           |                                <span data-ttu-id="3c931-144">示例</span><span class="sxs-lookup"><span data-stu-id="3c931-144">Example</span></span>                                 |
|---------------------------|------------------------------------|------------------------------------------------------------------------|
|        <span data-ttu-id="3c931-145">[RFC_NAME]</span><span class="sxs-lookup"><span data-stu-id="3c931-145">[RFC_NAME]</span></span>         |      <span data-ttu-id="3c931-146">[VERSION]/Rfc/[RFC_NAME]</span><span class="sxs-lookup"><span data-stu-id="3c931-146">[VERSION]/Rfc/[RFC_NAME]</span></span>      |     http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET      |
|    <span data-ttu-id="3c931-147">[RFC_NAME]响应</span><span class="sxs-lookup"><span data-stu-id="3c931-147">[RFC_NAME] Response</span></span>    | <span data-ttu-id="3c931-148">[VERSION]/Rfc/[RFC_NAME]/response</span><span class="sxs-lookup"><span data-stu-id="3c931-148">[VERSION]/Rfc/[RFC_NAME]/response</span></span>  | http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET/response |
|     <span data-ttu-id="3c931-149">RfcGetAttributes</span><span class="sxs-lookup"><span data-stu-id="3c931-149">RfcGetAttributes</span></span>      |     <span data-ttu-id="3c931-150">[VERSION]/RfcGetAttributes</span><span class="sxs-lookup"><span data-stu-id="3c931-150">[VERSION]/RfcGetAttributes</span></span>     |       http://Microsoft.LobServices.Sap/2007/03/RfcGetAttributes        |
| <span data-ttu-id="3c931-151">RfcGetAttributes Response</span><span class="sxs-lookup"><span data-stu-id="3c931-151">RfcGetAttributes Response</span></span> | <span data-ttu-id="3c931-152">[VERSION/RfcGetAttributes/response</span><span class="sxs-lookup"><span data-stu-id="3c931-152">[VERSION/RfcGetAttributes/response</span></span> |   http://Microsoft.LobServices.Sap/2007/03/RfcGetAttributes/response   |

 <span data-ttu-id="3c931-153">[VERSION] = 消息版本字符串;例如， http://Microsoft.LobServices.Sap/2007/03。</span><span class="sxs-lookup"><span data-stu-id="3c931-153">[VERSION] = The message version string; for example, http://Microsoft.LobServices.Sap/2007/03.</span></span>  

 <span data-ttu-id="3c931-154">[RFC_NAME] = RFC 调用; 的名称例如，RFC_CUSTOMER_GET。</span><span class="sxs-lookup"><span data-stu-id="3c931-154">[RFC_NAME] = The name of the RFC to be invoked; for example, RFC_CUSTOMER_GET.</span></span>  

## <a name="invoking-a-bapi-as-an-rfc-operation"></a><span data-ttu-id="3c931-155">RFC 操作的形式调用 BAPI</span><span class="sxs-lookup"><span data-stu-id="3c931-155">Invoking a BAPI as an RFC Operation</span></span>  
 <span data-ttu-id="3c931-156">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]显示 Bapi 作为 RFC 操作和业务对象的方法。</span><span class="sxs-lookup"><span data-stu-id="3c931-156">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces BAPIs both as RFC operations and as methods of business objects.</span></span> <span data-ttu-id="3c931-157">作为 RFC 操作按名称显示 Bapi。</span><span class="sxs-lookup"><span data-stu-id="3c931-157">As RFC operations, BAPIs are surfaced by name.</span></span> <span data-ttu-id="3c931-158">有关使用业务对象接口调用 Bapi 的详细信息，请参阅[sap Bapi 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="3c931-158">For more information about invoking BAPIs by using the business object interface, see [Operations on BAPIs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).</span></span>  

 <span data-ttu-id="3c931-159">以下 XML 显示了作为 RFC 调用 BAPI (BAPI_CUSTOMER_GETDETAIL2) 的消息结构。</span><span class="sxs-lookup"><span data-stu-id="3c931-159">The following XML shows the message structure for a BAPI (BAPI_CUSTOMER_GETDETAIL2) that is invoked as an RFC.</span></span> <span data-ttu-id="3c931-160">此操作的消息操作是： http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_CUSTOMER_GETDETAIL2。</span><span class="sxs-lookup"><span data-stu-id="3c931-160">The message action for this operation is: http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_CUSTOMER_GETDETAIL2.</span></span>  

```  
<BAPI_CUSTOMER_GETDETAIL2 xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <COMPANYCODE>1001</COMPANYCODE>  
  <CUSTOMERNO>0000001001</CUSTOMERNO>  
  <CUSTOMERBANKDETAIL>  
    <BAPICUSTOMER_02 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <CUSTOMER />  
      <BANK_CTRY />  
      <BANK_KEY />  
      <BANK_ACCT />  
      <CTRL_KEY />  
      <PARTNER_BK />  
      <COLL_AUTH />  
      <BANK_REF />  
    </BAPICUSTOMER_02>  
  </CUSTOMERBANKDETAIL>  
</BAPI_CUSTOMER_GETDETAIL2>  
```  

## <a name="see-also"></a><span data-ttu-id="3c931-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c931-161">See Also</span></span>  
 [<span data-ttu-id="3c931-162">消息和消息架构用于 mySAP Business Suite 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="3c931-162">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)