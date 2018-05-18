# Version 0.3.3 (2018-05-18)
- With Set-TppAttribute set to Overwrite by default, update New-TppCapiApplication to ensure our Consumers attribute update does not overwrite

# Version 0.3.2 (2018-05-17)
- initial cut at gathering workflow ticket details 
- resolve issue with New-TppSession not loading private functions 
- Update Set-TppAttribute to make overwrite the default behavior

# Version 0.3.1 (2018-05-17)
- Get-TppObjectConfig renamed to Get-TppAttribute 
- Add support for custom fields. Custom fields are retrieved upon server connect and stored in TppSession. 
Get-TppAttribute and Set-TppAttribute both support auto detection of a custom field. The custom field Label will be used in place of the Guid. 
- Modify Get-TppObject to search recursively by default 

# Version 0.2.8 (2018-05-09)
- finalize Set-TppAttribute, supports adding and overwriting values 
- Default DN to VED root in Get-TppObject, one less param to provide if doing a basic search 
- Fix New-TppCapiApplication to update Consumers attrib on the certificate 
- Help updates