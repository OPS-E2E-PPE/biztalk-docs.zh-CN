---
title: "适配器的自定义配置架构的示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31b188de-9363-4f4c-b40a-149ff59ddf8d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b11cb16c7b7ae9285b6ffb77c7177964d211482f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="examples-of-custom-configuration-schemas-for-adapters"></a><span data-ttu-id="4649a-102">适配器的自定义配置架构的示例</span><span class="sxs-lookup"><span data-stu-id="4649a-102">Examples of Custom Configuration Schemas for Adapters</span></span>
<span data-ttu-id="4649a-103">本节提供以下示例，介绍如何为适配器自定义配置架构：</span><span class="sxs-lookup"><span data-stu-id="4649a-103">This section provides the following examples for how to customize configuration schemas for adapters:</span></span>  
  
-   <span data-ttu-id="4649a-104">**示例 1**演示表示使用 baf:designer 和 baf:description 扩展适配器属性页的完整自定义 XSD 架构文件。</span><span class="sxs-lookup"><span data-stu-id="4649a-104">**Example 1** shows a complete custom XSD schema file representing an adapter property page using the baf:designer and baf:description extensions.</span></span>  
  
-   <span data-ttu-id="4649a-105">**示例 2**还使用 baf:designer 和 baf:description 扩展来演示如何创建的自定义属性值窗口**BatchSize**只接受介于 1 和 99 之间 （含） 之间的值的属性。</span><span class="sxs-lookup"><span data-stu-id="4649a-105">**Example 2** also uses the baf:designer and baf:description extensions to show how to create a custom property value window for the **BatchSize** property that only accepts values between 1 and 99, inclusive.</span></span>  
  
-   <span data-ttu-id="4649a-106">**示例 3**演示如何限制为 8 个字符 baf:Password。</span><span class="sxs-lookup"><span data-stu-id="4649a-106">**Example 3** shows how to limit the baf:Password to 8 characters.</span></span> <span data-ttu-id="4649a-107">默认情况下，它允许 22 个字符。</span><span class="sxs-lookup"><span data-stu-id="4649a-107">By default, it allows 22 characters.</span></span>  
  
-   <span data-ttu-id="4649a-108">**示例 4**演示如何实现对属性值的模式匹配约束，因为不支持 XSD 模式。</span><span class="sxs-lookup"><span data-stu-id="4649a-108">**Example 4** shows how to implement pattern-matching constraints on property values because XSD patterns are not supported.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="4649a-109">示例 1</span><span class="sxs-lookup"><span data-stu-id="4649a-109">Example 1</span></span>  
 <span data-ttu-id="4649a-110">该示例说明了一个完整的自定义 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="4649a-110">This example shows a complete custom XSD schema.</span></span> <span data-ttu-id="4649a-111">它使用 baf:designer 和 baf:description 扩展表示一个适配器属性页。</span><span class="sxs-lookup"><span data-stu-id="4649a-111">It represents an adapter property page using the baf:designer and baf:description extensions.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<xs:schema   targetNamespace="http://tempuri.org/XMLSchema.xsd"   
         elementFormDefault="qualified" xmlns="http://tempuri.org/XMLSchema.xsd"   
         xmlns:baf="BiztalkAdapterFramework.xsd"   
         xmlns:xs="http://www.w3.org/2001/XMLSchema"   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:import namespace="BiztalkAdapterFramework.xsd" />  
   <xs:element name="Send">  
      <xs:complexType>  
         <xs:sequence>  
            <xs:element name="directory" type="xs:string" />  
               <xs:annotation>  
                  <xs:appinfo>  
                     <baf:designer>  
                        <baf:description>Enter the directory that will receive sent files..  
                        </baf:description>  
                     </baf:designer>  
                  </xs:appinfo>  
               </xs:annotation>  
            </xs:element>  
            <xs:element name="fileName" type="" />  
            <xs:element name="sendBatchSize" type="xs:int" />  
            <xs:element name="fileCopyMode" type="CopyMode" />  
            <xs:element name="uri" type="xs:string" >  
               <xs:annotation>  
                  <xs:appinfo>  
                     <baf:designer>  
                        <baf:browsable show="false" />  
                     </baf:designer>  
                  </xs:appinfo>  
               </xs:annotation>  
            </xs:element>  
         </xs:sequence>  
      </xs:complexType>  
   </xs:element>  
   <xs:simpleType name="CopyMode">  
      <xs:restriction base="xs:string">  
         <xs:enumeration value="Append">  
            <xs:annotation>  
               <xs:documentation>= 0</xs:documentation>  
            </xs:annotation>  
         <xs:enumeration value="Create">  
            <xs:annotation>  
               <xs:documentation>= 1</xs:documentation>  
            </xs:annotation>  
         <xs:enumeration value="CreateNew">  
            <xs:annotation>  
               <xs:documentation>= 2</xs:documentation>  
            </xs:annotation>  
         </xs:enumeration>  
      </xs:restriction>  
   </xs:simpleType>  
</xs:schema>  
```  
  
## <a name="example-2"></a><span data-ttu-id="4649a-112">示例 2</span><span class="sxs-lookup"><span data-stu-id="4649a-112">Example 2</span></span>  
 <span data-ttu-id="4649a-113">此示例使用在 baf:designer 和 baf:description 扩展来演示如何创建的自定义属性值窗口**BatchSize**只接受介于 1 和 99 之间 （含） 之间的值的属性。</span><span class="sxs-lookup"><span data-stu-id="4649a-113">This example uses the baf:designer and baf:description extensions to show how to create a custom property value window for the **BatchSize** property that only accepts values between 1 and 99, inclusive.</span></span>  
  
```  
   <xs:element name="BatchSize">  
          <xs:simpleType>  
            <xs:annotation>  
              <xs:appinfo>  
                <baf:designer>  
                  <baf:displayname>Batch Size</baf:displayname>  
                  <baf:description>Enter the batch size (1-99)</baf:description>  
                </baf:designer>  
              </xs:appinfo>  
            </xs:annotation>  
            <xs:restriction base="xs:int">  
              <xs:minInclusive value="1" />  
              <xs:maxInclusive value="99" />  
            </xs:restriction>  
          </xs:simpleType>  
        </xs:element>  
```  
  
## <a name="example-3"></a><span data-ttu-id="4649a-114">示例 3</span><span class="sxs-lookup"><span data-stu-id="4649a-114">Example 3</span></span>  
 <span data-ttu-id="4649a-115">该示例说明如何将 baf:Password 限制为 8 个字符。</span><span class="sxs-lookup"><span data-stu-id="4649a-115">This example shows how to limit the baf:Password to 8 characters.</span></span> <span data-ttu-id="4649a-116">默认情况下，它允许 22 个字符。</span><span class="sxs-lookup"><span data-stu-id="4649a-116">By default, it allows 22 characters.</span></span>  
  
```  
<xs:element name="AdapterPassword">  
          <xs:simpleType>  
            <xs:annotation>  
              <xs:appinfo>  
                <baf:designer>  
                  <baf:displayname>Adapter Password</baf:displayname>  
                  <baf:description>Enter the password (up to 8 characters)</baf:description>  
                  <baf:editor assembly="%BTSROOT%\\Developer Tools\\Microsoft.BizTalk.Adapter.Framework.dll">Microsoft.BizTalk.Adapter.Framework.ComponentModel.PasswordUITypeEditor</baf:editor>  
                  <baf:converter assembly="%BTSROOT%\\Developer Tools\\Microsoft.BizTalk.Adapter.Framework.dll">Microsoft.BizTalk.Adapter.Framework.ComponentModel.PasswordTypeConverter</baf:converter>  
                </baf:designer>  
              </xs:appinfo>  
            </xs:annotation>  
            <xs:restriction base="xs:string">  
              <xs:maxLength value="8" />  
            </xs:restriction>  
          </xs:simpleType>  
        </xs:element>  
```  
  
## <a name="example-4"></a><span data-ttu-id="4649a-117">示例 4</span><span class="sxs-lookup"><span data-stu-id="4649a-117">Example 4</span></span>  
 <span data-ttu-id="4649a-118">此示例说明如何对属性值实现模式匹配约束，因为不支持 XSD 模式。</span><span class="sxs-lookup"><span data-stu-id="4649a-118">This example shows how to implement pattern-matching constraints on property values because XSD patterns are not supported.</span></span>  
  
 <span data-ttu-id="4649a-119">如字段**ClientIdentifier**始终是三个字符的数值字符串。</span><span class="sxs-lookup"><span data-stu-id="4649a-119">Fields such as **ClientIdentifier** are always a three-character numeric string.</span></span> <span data-ttu-id="4649a-120">属性值 10 无效，而 010 有效。</span><span class="sxs-lookup"><span data-stu-id="4649a-120">A property value of 10 is not valid, whereas 010 is valid.</span></span> <span data-ttu-id="4649a-121">以下配置架构片段定义**ClientIdentifier**属性。</span><span class="sxs-lookup"><span data-stu-id="4649a-121">The following configuration schema fragment defines a **ClientIdentifier** property.</span></span> <span data-ttu-id="4649a-122">**ClientIdentifierConverter**类，实现您的适配器集，在实现模式匹配。</span><span class="sxs-lookup"><span data-stu-id="4649a-122">The **ClientIdentifierConverter** class, implemented in your adapter assembly, implements pattern matching.</span></span> <span data-ttu-id="4649a-123">在这个例子中，自定义类型转换器将值限制为恰好 3 位的字符串（000 到 999）。</span><span class="sxs-lookup"><span data-stu-id="4649a-123">In this case, the custom type converter restricts values to a string of exactly three digits (000 to 999).</span></span> <span data-ttu-id="4649a-124">在配置架构中，请确保 baf:converter 节点正确设置了程序集和类型全名。</span><span class="sxs-lookup"><span data-stu-id="4649a-124">In the configuration schema, make sure the baf:converter node has the assembly and type full name set correctly.</span></span> <span data-ttu-id="4649a-125">如果用户尝试输入无效值，在属性页中发生验证错误时，将会弹出一个异常消息。</span><span class="sxs-lookup"><span data-stu-id="4649a-125">If the user attempts to enter a value that is not valid, an exception message pops up when a validation error occurs in the property page.</span></span>  
  
 <span data-ttu-id="4649a-126">您可以在适配器属性页配置架构中使用以下代码。</span><span class="sxs-lookup"><span data-stu-id="4649a-126">You can use the following code in the adapter property page configuration schemas.</span></span>  
  
```  
        <xs:element name="ClientIdentifier" type="xs:string">  
          <xs:annotation>  
            <xs:appinfo>  
              <baf:designer>  
                <baf:displayname>Adapter Client</baf:displayname>  
                <baf:description>Enter the Adapter Client (3 digit string)</baf:description>  
                <baf:converter assembly="%BTSROOT%\\Developer Tools\\Microsoft.BizTalk.TestAdapter.dll">Microsoft.BizTalk.TestAdapter.ClientIdentifierConverter</baf:converter>  
              </baf:designer>  
            </xs:appinfo>  
          </xs:annotation>  
        </xs:element>  
```  
  
 <span data-ttu-id="4649a-127">可在适配器程序集中放置以下代码。</span><span class="sxs-lookup"><span data-stu-id="4649a-127">You can place the following code in your adapter assembly.</span></span>  
  
```  
using System;  
using System.ComponentModel;  
using System.Globalization;  
using System.Text.RegularExpressions;  
  
namespace Microsoft.BizTalk.TestAdapter  
{  
       /// <summary>  
       /// Summary description for ClientIdentifierConverter.  
       /// </summary>  
       public class ClientIdentifierConverter : System.ComponentModel.StringConverter   
       {  
              private void Validate(string value)  
              {  
                     Regex regex = new Regex(@"^\d{3}$"); // ^=begin, \d=digit, {3}=exactly 3 occurrences, $=end  
                     Match match = regex.Match((string)value);  
                     if (!match.Success)  
                     {  
                           throw new ApplicationException("Value does not match pattern \"" + regex.ToString() + "\".");  
                     }  
              }  
  
              public override object ConvertFrom(ITypeDescriptorContext context, CultureInfo culture, object value)  
              {  
                     if (value is string)  
                     {  
                           this.Validate((string)value);  
                     }  
                     return base.ConvertFrom(context, culture, value);  
              }  
  
              public override object ConvertTo(ITypeDescriptorContext context, CultureInfo culture, object value, Type destinationType)  
              {  
                     if (typeof(string) == destinationType && value is string)  
                     {  
                           this.Validate((string)value);  
                     }  
                     return base.ConvertTo(context, culture, value, destinationType);  
              }  
       }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="4649a-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4649a-128">See Also</span></span>  
 [<span data-ttu-id="4649a-129">适配器 Framework 配置架构扩展</span><span class="sxs-lookup"><span data-stu-id="4649a-129">Adapter Framework Configuration Schema Extensions</span></span>](../core/adapter-framework-configuration-schema-extensions.md)