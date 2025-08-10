# ����AI�A�v�� �݌v��

---

## 1. �T�v

- ���[�U�[�����v���ԁE�ޗ��E�J�e�S�����w�肵�Č��������ł���Web�A�v��  
- ���[�h��2���  
  - AI���[�h�iOpenAI API�Ń��j���[�����j  
  - �������[�h�iGoogle �X�v���b�h�V�[�g�ɕۑ����ꂽ�ߋ����j���[�����j  
- �t�����g�G���h�̓��X�|���V�uHTML�i�X�}�z�Ή��j  
- �o�b�N�G���h��FastAPI��Render.com�Ƀf�v���C  
- Google Apps Script�iGAS�j�ŃX�v���b�h�V�[�g�A�g������  

---

## 2. �V�X�e���\��

| �R���|�[�l���g           | �Z�p / �T�[�r�X            | ����                                  |
|------------------------|--------------------------|-------------------------------------|
| �t�����g�G���h           | HTML/CSS/JavaScript      | ���̓t�H�[���\���AAPI�Ăяo���A���ʕ\��         |
| �o�b�N�G���hAPI          | Python FastAPI           | ���N�G�X�g�󂯎��AOpenAI�EGAS�A�g����         |
| OpenAI API             | OpenAI                  | AI������Ă̐���                      |
| Google Apps Script(GAS) | Google Apps Script       | �X�v���b�h�V�[�g�A�N�Z�X�A���������E�o�^����        |
| �X�v���b�h�V�[�g         | Google Sheets            | �ߋ��̌����f�[�^�̕ۑ��E�Ǘ�                |
| �z�X�e�B���O             | Render.com, GitHub Pages | FastAPI�̃z�X�e�B���O(Render)�A�ÓIHTML�z�M(GitHub Pages) |

---

## 3. �ڍא݌v

### 3-1. �t�����g�G���h

- ���͍���  
  - ���[�h�i`ai` or `history`�j: select  
  - ���v���ԁi���j: number����  
  - �ޗ�: �J���}��؂�e�L�X�g  
  - �J�e�S��: select�i�a�H�A���؁A�m�H�A���̑��j  

- �{�^�������� `/search` �G���h�|�C���g��POST  
- ���ʂ̓e�[�u���`���ŕ\��  
- �X�}�z�Ή��i���X�|���V�u�f�U�C���j  

---

### 3-2. �o�b�N�G���h�iFastAPI�j

- `/search` (POST)  
  - ���N�G�X�gJSON��  
    ```json
    {
      "mode": "ai",
      "keywords": {
        "time": "30",
        "ingredients": "�ؓ�, �ɂ񂶂�",
        "category": "�m�H"
      }
    }
    ```
  - `mode == "ai"` �̏ꍇ  
    - OpenAI API�Ƀv�����v�g���M���A������Č��ʂ��擾  
    - JSON�e�L�X�g�Ńt�����g�֕ԋp  
  - `mode == "history"` �̏ꍇ  
    - GAS��Webhook URL�֌����L�[���[�h�𑗐M  
    - �X�v���b�h�V�[�g����Y�����j���[���擾�E�o�^�����ʕԋp  
- CORS�ݒ肠��i�t�����g�̃I���W�����j  

---

### 3-3. Google Apps Script (GAS)

- doPost(e)  
  - POST�f�[�^���p�[�X���A�����L�[���[�h���擾  
  - �X�v���b�h�V�[�g�̃f�[�^�͈͂𑖍��������ɍ������j���[�𒊏o  
  - ���ʂ�JSON�ŕԂ�  
  - �Y���Ȃ��̏ꍇ�̓L�[���[�h��V�K�s�ɕۑ�  
- �X�v���b�h�V�[�g��\����  
  - timestamp, time, ingredients, category, found, menu_json  

---

## 4. API�d�l

| �G���h�|�C���g | ���\�b�h | ���͗� (JSON)                             | �o�͗� (JSON)                                  | ���l                      |
|---------------|---------|-----------------------------------------|----------------------------------------------|-------------------------|
| `/search`     | POST    | See ��L��3-2���N�G�X�g��                 | AI or �X�v���b�h�V�[�g���ʂ�JSON                  | ���[�h�ɂ���ď����𕪂���       |

---

## 5. �f�v���C�E���ݒ�

| ����                   | ���e                                  |
|----------------------|-------------------------------------|
| FastAPI�z�X�e�B���O        | Render.com                           |
| ���ϐ�                | OPENAI_API_KEY�iOpenAI�L�[�j          |
|                      | GAS_WEBHOOK�iGAS�̃E�F�u�A�v��URL�j     |
| �ÓIHTML�z�X�e�B���O        | GitHub Pages�iindex.html��z�u�j          |
| Google �X�v���b�h�V�[�gID   | GAS�R�[�h����`SPREADSHEET_ID`�ɐݒ�       |

---

## 6. ����̊g����

- AI�̃��X�|���X��JSON��͂���UI�ō\�����\��  
- �ޗ���J�e�S���̎����⊮��^�O����UI  
- ���������̍i�荞�݋����i������v�A���������j  
- ���[�U�[�F�؁E�A�N�Z�X���������iGAS�̔F�؂�API�L�[�Ǘ��j  
- �X�}�zUI�̉��P�i�����菇�̐܂肽���ݕ\���Ȃǁj  

---

