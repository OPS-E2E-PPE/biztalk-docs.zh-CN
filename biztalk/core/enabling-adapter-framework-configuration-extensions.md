---
title: "启用适配器 Framework 配置扩展 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 851f4a20-502d-45f8-9647-13bec33fa460
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 346bbc3d4d136ad7116a68b3c57a47566f258a68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="enabling-adapter-framework-configuration-extensions"></a><span data-ttu-id="97fa2-102">使适配器 Framework 配置扩展</span><span class="sxs-lookup"><span data-stu-id="97fa2-102">Enabling Adapter Framework Configuration Extensions</span></span>
<span data-ttu-id="97fa2-103">BizTalk 适配器框架提供多种扩展，为用户带来更多便利。</span><span class="sxs-lookup"><span data-stu-id="97fa2-103">The BizTalk Adapter Framework provides several extensions to improve the user experience.</span></span> <span data-ttu-id="97fa2-104">若要使用这些扩展，导入的框架的架构，BiztalkAdapterFramework.xsd。</span><span class="sxs-lookup"><span data-stu-id="97fa2-104">To use these extensions, import the framework's schema, BiztalkAdapterFramework.xsd.</span></span> <span data-ttu-id="97fa2-105">导入架构使你能够访问修饰和专用的类型，以及在适配器的配置架构中使用它们，如下所述。</span><span class="sxs-lookup"><span data-stu-id="97fa2-105">Importing the schema enables you to access decorations and specialized types and to use them in the adapter's configuration schema, as described below.</span></span> <span data-ttu-id="97fa2-106">下面的代码演示如何导入该架构：</span><span class="sxs-lookup"><span data-stu-id="97fa2-106">The following code shows how to import the schema:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?><xs:schema   targetNamespace="http://tempuri.org/XMLSchema.xsd"   
         elementFormDefault="qualified" xmlns="http://tempuri.org/XMLSchema.xsd"   
         xmlns:baf="BiztalkAdapterFramework.xsd"   
         xmlns:xs="http://www.w3.org/2001/XMLSchema"   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:import namespace="BiztalkAdapterFramework.xsd" />  
. . .  
</xs:schema>  
```  
  
## <a name="importing-the-biztalk-adapter-framework-extensions-schema-xsd"></a><span data-ttu-id="97fa2-107">导入 BizTalk 适配器框架扩展架构 XSD</span><span class="sxs-lookup"><span data-stu-id="97fa2-107">Importing the BizTalk Adapter Framework Extensions Schema XSD</span></span>  
 <span data-ttu-id="97fa2-108">通过导入适配器框架扩展架构 XSD，你可以使用修饰如\<baf:FileName > 作为元素的类型，它显示的文件名称弹出编辑元素时。</span><span class="sxs-lookup"><span data-stu-id="97fa2-108">By importing the Adapter Framework extensions schema XSD, you can use decorations such as \<baf:FileName> as an element's type, which shows the file name pop-up when editing the element.</span></span>  
  
 <span data-ttu-id="97fa2-109">其他修饰控制属性在界面中的显示方式。</span><span class="sxs-lookup"><span data-stu-id="97fa2-109">Additional decorations control the display of the property in the interface.</span></span> <span data-ttu-id="97fa2-110">\<Baf:description > 修饰，例如，将帮助文本添加到元素。</span><span class="sxs-lookup"><span data-stu-id="97fa2-110">The \<baf:description> decoration, for example, adds help text to the element.</span></span> <span data-ttu-id="97fa2-111">\<Baf:description > 修饰的属性页的底部显示的文本。</span><span class="sxs-lookup"><span data-stu-id="97fa2-111">The \<baf:description> decoration displays the text at the bottom of the property page.</span></span> <span data-ttu-id="97fa2-112">\<Baf： 可浏览 > 修饰隐藏接口中的元素。</span><span class="sxs-lookup"><span data-stu-id="97fa2-112">The \<baf:browsable> decoration hides an element from the interface.</span></span> <span data-ttu-id="97fa2-113">下面的代码显示如何在配置架构中使用这些元素：</span><span class="sxs-lookup"><span data-stu-id="97fa2-113">The following code shows how you can use these elements within a configuration schema:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?><xs:schema   targetNamespace="http://tempuri.org/XMLSchema.xsd"   
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
  
## <a name="see-also"></a><span data-ttu-id="97fa2-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97fa2-114">See Also</span></span>  
 [<span data-ttu-id="97fa2-115">适配器 Framework 配置架构扩展</span><span class="sxs-lookup"><span data-stu-id="97fa2-115">Adapter Framework Configuration Schema Extensions</span></span>](../core/adapter-framework-configuration-schema-extensions.md)