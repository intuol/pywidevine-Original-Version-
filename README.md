pywidevine (original version)
===============
**The original version of pywidevine used in Python related DRM downloading tools. This version unlike rlaphoenix's pywidevine gets keys only while that fork gets keys and makes .wvd files.**


How to use:
===============

def WV_Function(pssh, lic_url, cert_b64="cert.b64"):
    wvdecrypt = WvDecrypt(init_data_b64=pssh, cert_data_b64=cert_b64, device=deviceconfig.device_devicehere)                   
    widevine_license = requests.post(url=lic_url, data=wvdecrypt.get_challenge(), headers=headers.headers)
    license_b64 = b64encode(widevine_license.content)
    wvdecrypt.update_license(license_b64)
    Correct, keyswvdecrypt = wvdecrypt.start_process()
    if Correct:
        return Correct, keyswvdecrypt   
correct, keys = WV_Function(pssh, lic_url)

This above functions getting keys.

