---
title: 适配器 WSDL 文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d4b35c0-1e4b-4106-8921-29d14f976d65
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67b341372e39fc9f834c2240127d10946def76a8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361162"
---
# <a name="adapter-wsdl-files"></a><span data-ttu-id="a838c-102">适配器 WSDL 文件</span><span class="sxs-lookup"><span data-stu-id="a838c-102">Adapter WSDL Files</span></span>
<span data-ttu-id="a838c-103">在添加适配器元数据向导中选择和输入上的 Web 服务描述语言 (WSDL) 文件**选择导入的服务**页。</span><span class="sxs-lookup"><span data-stu-id="a838c-103">In the Add Adapter Metadata Wizard the Web Services Description Language (WSDL) file is selected and input on the **Select Services to Import** page.</span></span> <span data-ttu-id="a838c-104">该向导将读取 WSDL 文件由服务公开，并由用户选择。</span><span class="sxs-lookup"><span data-stu-id="a838c-104">The wizard reads the WSDL files exposed by the service and selected by the user.</span></span> <span data-ttu-id="a838c-105">然后，它将创建并在 BizTalk 项目中添加一个 XSD 文件和业务流程。</span><span class="sxs-lookup"><span data-stu-id="a838c-105">It then creates and adds an XSD file and an orchestration in the BizTalk project.</span></span>  
  
 <span data-ttu-id="a838c-106">在示例文件适配器中，Service1.wsdl 文件包含的 XSD 定义的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将添加到项目。</span><span class="sxs-lookup"><span data-stu-id="a838c-106">In the sample file adapter, the Service1.wsdl file contains the XSD definitions that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adds to the project.</span></span> <span data-ttu-id="a838c-107">您可以选择修改该 Service1.wsdl 文件或创建自己的 WSDL 文件，其中包含要添加到 BizTalk 项目的 XSD 定义。</span><span class="sxs-lookup"><span data-stu-id="a838c-107">You may choose to modify the Service1.wsdl file or create your own WSDL file that contains the XSD definitions to add to your BizTalk project.</span></span>  
  
 <span data-ttu-id="a838c-108">以下代码摘自 Service1.wsdl 文件：</span><span class="sxs-lookup"><span data-stu-id="a838c-108">The following code is from the Service1.wsdl file:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<definitions xmlns:http="http://schemas.xmlsoap.org/wsdl/http/" xmlns:soap="http://schemas.xmlsoap.org/wsdl/soap/" xmlns:s="http://www.w3.org/2001/XMLSchema" xmlns:s0="http://tempuri.org/" xmlns:soapenc="http://schemas.xmlsoap.org/soap/encoding/" xmlns:tm="http://microsoft.com/wsdl/mime/textMatching/" xmlns:mime="http://schemas.xmlsoap.org/wsdl/mime/" targetNamespace="http://tempuri.org/" xmlns="http://schemas.xmlsoap.org/wsdl/">  
  <types>  
    <s:schema elementFormDefault="qualified" targetNamespace="http://tempuri.org/">  
      <s:element name="GetTaxID">  
        <s:complexType />  
      </s:element>  
      <s:element name="GetTaxIDResponse">  
        <s:complexType>  
          <s:sequence>  
            <s:element minOccurs="0" maxOccurs="1" name="GetTaxIDResult" type="s:string" />  
          </s:sequence>  
        </s:complexType>  
      </s:element>  
      <s:element name="GetPayStub">  
        <s:complexType />  
      </s:element>  
      <s:element name="GetPayStubResponse">  
        <s:complexType>  
          <s:sequence>  
            <s:element minOccurs="0" maxOccurs="1" name="GetPayStubResult" type="s:string" />  
          </s:sequence>  
        </s:complexType>  
      </s:element>  
      <s:element name="GetTaxInfo">  
        <s:complexType />  
      </s:element>  
  
```