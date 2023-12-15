# Flooded Grounds URP Conversion  

There is a great asset in the unity asset store called 'Flooded Grounds' by Sandro T. which was created for built-in rendering pipeline. I did some work to convert the materials to URP so the asset will render if you are using that pipeline.  

[https://assetstore.unity.com/packages/3d/environments/flooded-grounds-48529](https://assetstore.unity.com/packages/3d/environments/flooded-grounds-48529)  

Just like I converted the amazing [Sun Temple](https://github.com/blastfurnace360/sun_temple_urp), each of the surface shaders were replaced with shadergraph versions. The 'Flooded Grounds' asset doesn't use as many surface shaders as 'Sun Temple' and a lot of the work was already done after running the unity render pipeline converter.  

Steps to import -  
1-- using unity hub, create a new URP project  
2-- import the 'flooded grounds' asset from the asset store - uncheck the box for the 'post processing' folder to avoid an error (URP does not use this post processing anyway)  
3-- clone this repository and import the unitypackage file into your project (click 'assets' menu, select 'import package' -> 'import custom package', then navigate to the flooded_grounds_URP.unitypackage file)  
4-- you will see that this overwrites the terrain layers and terrain files, the materials, adds some shadergraphs, and a new scene called SceneA_URP.unity  
5-- open the SceneA_URP and press play  

notes - 'Flooded Grounds' has a lot of trees which were made with 'tree creator' which uses shaders that don't render in URP. There aren't any replacement shaders so I duplicated the terrain and removed all of the trees in the URP scene. These are nice trees and you can convert them to URP using 'the vegetation engine'.    

Like the 'Sun Temple' conversion, the grass looks strange because it's supposed to use a custom shader. You can't use custom shaders for terrain details in URP easily, but if you have 'nature renderer' it will allow it. 

The grass can be fixed by enabling GPU instancing on the grass details. Or download Terrain Sample Assets and replace the grass.

bonus - I added a unitypackage for the cactus pack which is another asset from Sandro T.
