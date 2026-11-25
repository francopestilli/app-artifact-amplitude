# app-artifact-amplitude 

<!-- brainlife-app:begin (generated from the App manifest; edit the manifest, not this block) -->

> **Rejects MEG/EEG epochs whose peak-to-peak amplitude exceeds reject thresholds or falls below flat thresholds per channel type, with MNE-Python drop_bad, and outputs the cleaned epochs and a drop-log plot.**

Parses reject and flat criteria given as 'type=value' pairs separated by semicolons (e.g. grad=4000e-13;mag=4e-12;eeg=150e-6) and calls epochs.drop_bad. Use it as a simple amplitude-based artifact rejection after epoching. Both criteria strings must list the same channel types in the same order, because the flat thresholds are keyed by the reject criteria's channel types.

| | |
|---|---|
| 📥 **Inputs** | `neuro/meeg/mne/epochs` |
| 📤 **Outputs** | `neuro/meeg/mne/epochs` · `generic/image/png` |
| 🐳 **Container** | `brainlife/mne:0.23dev` |
| ⚙️ **Resources** | 8 CPUs |
| 🔗 **Run it** | [doi.org/10.25663/brainlife.app.653](https://doi.org/10.25663/brainlife.app.653) |

#### 📥 Inputs

| Input | Datatype | Required | Description |
|---|---|---|---|
| `epo` | `neuro/meeg/mne/epochs` | yes | Epoched MEG/EEG data in MNE epochs .fif format. |

#### 📤 Outputs

| Output | Datatype | Description |
|---|---|---|
| `out_dir` | `neuro/meeg/mne/epochs` | Epochs (meg-epo.fif) after dropping those that violate the amplitude criteria. |
| `out_figs` | `generic/image/png` | Drop-log plot showing why epochs were rejected. |

<details>
<summary><b>⚙️ Parameters</b> (2)</summary>

| Parameter | Type | Default | Description |
|---|---|---|---|
| `flat_criteria` | string |  | a string that contains the flat criteria (minimum acceptable peak-to-peak amplitudes for each channel type in an epoch) |
| `reject_criteria` | string |  | a string that contains the reject criteria (maximum acceptable peak-to-peak amplitudes for each channel type in an epoch) |

</details>

📚 **References used by this App:**
- Avesani P, et al. The open diffusion data derivatives, brain data upcycling via integrated publishing of derivatives and reproducible open cloud services. Sci Data 6:69 (2019). [doi:10.1038/s41597-019-0073-y](https://doi.org/10.1038/s41597-019-0073-y)

<!-- brainlife-app:end -->

This is the repository of a Brainlife App for rejecting Epochs based on channel amplitude (https://mne.tools/stable/auto_tutorials/preprocessing/20_rejecting_bad_data.html#rejecting-epochs-based-on-channel-amplitude).

# Documentation

Rejecting epochs, based on signal amplitude thresholds for each channel type.

#### Input files are:
  * an epoch file in `.fif` format,

 
#### Input parameters are:
  * a string that contains the reject criteria (maximum acceptable peak-to-peak amplitudes for each channel type in an epoch),
  * a string that contains the flat criteria (minimum acceptable peak-to-peak amplitudes for each channel type in an epoch),
      


#### Ouput files are:
  * a `.fif` epoch file after rejection,


### Authors
- [Saeed Zahran](saeedzahran@hotmail.com)

### Contributors
- [Saeed Zahran](saeedzahran@hotmail.com)

### Funding Acknowledgement
brainlife.io is publicly funded and for the sustainability of the project it is helpful to Acknowledge the use of the platform. We kindly ask that you acknowledge the funding below in your code and publications. Copy and past the following lines into your repository when using this code.

[![NSF-BCS-1734853](https://img.shields.io/badge/NSF_BCS-1734853-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1734853)
[![NSF-BCS-1636893](https://img.shields.io/badge/NSF_BCS-1636893-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1636893)
[![NSF-ACI-1916518](https://img.shields.io/badge/NSF_ACI-1916518-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1916518)
[![NSF-IIS-1912270](https://img.shields.io/badge/NSF_IIS-1912270-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1912270)
[![NIH-NIBIB-R01EB029272](https://img.shields.io/badge/NIH_NIBIB-R01EB029272-green.svg)](https://grantome.com/grant/NIH/R01-EB029272-01)

### Citations
1. Avesani, P., McPherson, B., Hayashi, S. et al. The open diffusion data derivatives, brain data upcycling via integrated publishing of derivatives and reproducible open cloud services. Sci Data 6, 69 (2019). [https://doi.org/10.1038/s41597-019-0073-y](https://doi.org/10.1038/s41597-019-0073-y)
2. Taulu S. and Kajola M. Presentation of electromagnetic multichannel data: The signal space separation method. Journal of Applied Physics, 97 (2005). [https://doi.org/10.1063/1.1935742](https://doi.org/10.1063/1.1935742)
3. Taulu S. and Simola J. Spatiotemporal signal space separation method for rejecting nearby interference in MEG measurements. Physics in Medicine and Biology, 51 (2006). [https://doi.org/10.1088/0031-9155/51/7/008](https://doi.org/10.1088/0031-9155/51/7/008)
