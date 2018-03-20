# Delivering ad icon with VAST 3

VAST 3.0 introduces the <Icons> element, which is offered under the <Linear> creative element for both Inline and Wrapper ads.

The \<Icons\> element is a container for the <Icon> elements. The \<Icon\> element must contain a resource element that is one of: \<StaticResource\>, \<IFrameResource\>, or \<HTMLResource\>.

## The CrownPeak icon is implemented with a \<IFrameResource\>

This an example of a typical Icons tag.

```xml
<Icons>
    <Icon duration="00:00:05" program="AdChoices" height="20" width="122" xPosition="right" yPosition="0">
        <IFrameResource>
            <![CDATA[//c.evidon.com/vast-iframe.html?;coid=242;nid=115053;position=top-right]]>
        </IFrameResource>
    </Icon>
</Icons>```


The fixed XML attributes are: program="AdChoices" height="20" width="122". These values *must not change*. The height and width correspond to an iframe that contains the icons.  It is just large enough for the icon.

*Variable XML attributes* - xPosition (possible values: left, right), yPositon (possible values: top, bottom)

*Query String*
In \<IFrameResource\> there is a CDATA wrapped url with query string values attached. Values are:
⋅⋅*coid
⋅⋅*nid
⋅⋅*position (possible values: top-left, top-right, bottom-left, bottom-right).  This must correspond with the XML position attributes

A protocol of _https_ or no protocol at all are acceptable for the link to vast-iframe.html. _http_ is not accepatable

### What does iframe_durly.html actually do?
It injects the durly script takes with the  query string values tacked on.




[VAST3]: https://www.iab.com/wp-content/uploads/2015/06/VASTv3_0.pdf